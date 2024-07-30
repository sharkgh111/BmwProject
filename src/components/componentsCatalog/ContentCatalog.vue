<template>
 <div class="content-block">
    <div class="catalog-content">
        <div class="content-container">
            <div class="select-content">
                <SelBlock 
                    :series="series" 
                    @select-series="selectSeria" 
                />
                <MainBlock 
                    :selectedSeria="selectedSeria" 
                    :models="models"
                    @add-to-bookmarks="addBookmark"
                    @add-to-favorites="addFavorite"
                />
                <SideBar
                    :bookmarks="bookmarks"
                    :numCards="numCards"
                    @remove-bookmark="removeAllBookmark"
                />
            </div>
        </div>
    </div>
 </div>
</template>

<style scoped>

    .catalog-content {
        padding: 20px 0;
        background: rgb(21,51,125);
        background: linear-gradient(99deg, rgb(0, 20, 70) 20%, rgba(0,12,37,1) 70%);
        border-top: 1px solid #c0cbff62;
        border-bottom: 1px solid #c0cbff62;
    }

    .select-content {
        display: flex;
        align-items: center;
        justify-content: center;
        flex-direction: row;
        max-width: 100%;
    }

</style>

<script>

import SelBlock from './SelectBlock.vue';
import MainBlock from './MainCatalogBlock.vue';
import SideBar from './SideBar.vue';

export default {
    name: 'Catalog',
    components: {
        SelBlock,
        MainBlock,
        SideBar
    },
    data() {
        return {
            bookmarks: [],
            series: [
                { name: 'BMW I', url: "/logo/bmwilogo.png" },
                { name: 'BMW M', url: "/logo/bmwmlogo.png" },
                { name: 'BMW X', url: "/logo/bmwxlogo.png" },
                { name: 'BMW IX', url: "/logo/bmwixlogo.png" },
            ],
            models: {
                'BMW IX': [
                    { id: 1, name: 'BMW X1', logo: '/images/Bmwmodel/bmwx1.png', class: 'bmwx1',
                        power: '220HP', speed: '200km/h', encapacity: '1.5L', entype: 'I3', isBookmarked: false, isFavorite: false },
                    { id: 2, name: 'BMW iX1', logo: '/images/Bmwmodel/bmwix1.png', class: 'bmwix1',
                        power: '313HP', speed: '180km/h', encapacity: 'Missing', entype: 'Missing', isBookmarked: false, isFavorite: false 
                     },
                    { id: 3, name: 'BMW iX3', logo: '/images/Bmwmodel/bmwix3.png', class: 'bmwix3',
                        power: '287HP', speed: '180km/h', encapacity: 'Missing', entype: 'Missing', sBookmarked: false, isFavorite: false 
                     },
                    { id: 4, name: 'BMW iX M60', logo: '/images/Bmwmodel/bmwixm60.png', class: 'bmwixm60',
                        power: '619HP', speed: '250km/h', encapacity: 'Missing', entype: 'Missing', isBookmarked: false, isFavorite: false 
                     }
                ],
                'BMW I': [
                    { id: 1, name: 'BMW i216', logo: '/images/Bmwmodel/bmwi216.png', class: 'bmwi216',
                        power: '102HP', speed: '205km/h', encapacity: '1.5L', entype: 'I3', isBookmarked: false, isFavorite: false },
                    { id: 2, name: 'BMW i420', logo: '/images/Bmwmodel/bmwi420.png', class: 'bmwi420',
                        power: '340HP', speed: '200km/h', encapacity: 'Missing', entype: 'Missing', isBookmarked: false, isFavorite: false },
                    { id: 3, name: 'BMW i420 M50', logo: '/images/Bmwmodel/bmwi420m50.png', class: 'bmwi420m50',
                        power: '544HP', speed: '225km/h', encapacity: 'Missing', entype: 'Missing', isBookmarked: false, isFavorite: false },
                    { id: 4, name: 'BMW i540', logo: '/images/Bmwmodel/bmwi5.png', class: 'bmwi5',
                        power: '350HP', speed: '250km/h', encapacity: '3.3L', entype: 'V6', isBookmarked: false, isFavorite: false },
                    { id: 5, name: 'BMW i540 M60', logo: '/images/Bmwmodel/bmwi5m60.png', class: 'bmwi5m60',
                        power: '340HP', speed: '250km/h', encapacity: 'Missing', entype: 'Missing', isBookmarked: false, isFavorite: false },
                    { id: 6, name: 'BMW i760', logo: '/images/Bmwmodel/bmwi760.png', class: 'bmwi760',
                        power: '530HP', speed: '280km/h', encapacity: 'Missing', entype: 'Missing', isBookmarked: false, isFavorite: false },
                    { id: 7, name: 'BMW i740d Sedan', logo: '/images/Bmwmodel/bmwi740dsedan.png', class: 'bmwi740sed',
                        power: '340HP', speed: '220km/h', encapacity: 'Missing', entype: 'Missing', isBookmarked: false, isFavorite: false },
                ],
                'BMW X': [
                    { id: 1, name: 'BMW X2', logo: '/images/Bmwmodel/bmwx2.png', class: 'bmwx2',
                        power: '192HP', speed: '240km/h', encapacity: '2.0L', entype: 'I4', isBookmarked: false, isFavorite: false },
                    { id: 2, name: 'BMW X2 M350i ', logo: '/images/Bmwmodel/bmwx2m350i.png', class: 'bmwx2m',
                        power: '306HP', speed: '250km/h', encapacity: '2.0L', entype: 'I4', isBookmarked: false, isFavorite: false },
                    { id: 3, name: 'BMW X3', logo: '/images/Bmwmodel/bmwx3.png', class: 'bmwx3',
                        power: '360HP', speed: '~250km/h', encapacity: '2.0L-3.0L', entype: 'I4-V6', isBookmarked: false, isFavorite: false },
                    { id: 4, name: 'BMW X3M', logo: '/images/Bmwmodel/bmwx3m.png', class: 'bmwx3m',
                        power: '510HP', speed: '280km/h', encapacity: '3.0L', entype: 'V6', isBookmarked: false, isFavorite: false },
                    { id: 5, name: 'BMW X4', logo: '/images/Bmwmodel/bmwx4.png', class: 'bmwx4',
                        power: '280HP', speed: '~260km/h', encapacity: '2.0L', entype: 'I4-V6', isBookmarked: false, isFavorite: false },
                    { id: 6, name: 'BMW X4M', logo: '/images/Bmwmodel/bmwx4m.png', class: 'bmwx4m',
                        power: '480HP', speed: '280km/h', encapacity: '3.0L', entype: 'V6', isBookmarked: false, isFavorite: false },
                    { id: 7, name: 'BMW X5 (2023)', logo: '/images/Bmwmodel/bmwx5.png', class: 'bmwx5',
                        power: '450HP', speed: '~260km/h', encapacity: '3.0L', entype: 'V6-V8', isBookmarked: false, isFavorite: false },
                    { id: 8, name: 'BMW X5M', logo: '/images/Bmwmodel/bmwx5m.png', class: 'bmwx5m',
                        power: '610HP', speed: '290km/h', encapacity: '4.4L', entype: 'V8', isBookmarked: false, isFavorite: false },
                    { id: 9, name: 'BMW X6', logo: '/images/Bmwmodel/bmwx6.png', class: 'bmwx6',
                        power: '523HP', speed: '260km/h', encapacity: '3.0L', entype: 'V6-V8', isBookmarked: false, isFavorite: false },
                    { id: 10, name: 'BMW X7 40i', logo: '/images/Bmwmodel/bmwx7.png', class: 'bmwx7',
                        power: '400HP', speed: '260km/h', encapacity: '3.0L', entype: 'V6', isBookmarked: false, isFavorite: false },
                    { id: 11, name: 'BMW XM', logo: '/images/Bmwmodel/bmwxm.png', class: 'bmwxm',
                        power: '740HP', speed: '320km/h', encapacity: '4.4L', entype: 'V8', isBookmarked: false, isFavorite: false },
                ],
                'BMW M': [
                    { id: 1, name: 'BMW M2 Coupe', logo: '/images/Bmwmodel/bmwm2coupe.png', class: 'bmwm2coupe',
                        power: '405HP', speed: '280+ km/h', encapacity: '3.0L', entype: 'V6', isBookmarked: false, isFavorite: false },
                    { id: 2, name: 'BMW M2 CS', logo: '/images/Bmwmodel/bmwm2cs.png', class: 'bmwm2cs',
                        power: '450HP', speed: '280+ km/h', encapacity: '3.0L', entype: 'V6', isBookmarked: false, isFavorite: false },
                    { id: 3, name: 'BMW M3 Sedan', logo: '/images/Bmwmodel/bmwm3sedan.png', class: 'bmwm3sedan',
                        power: '473HP', speed: '250km/h', encapacity: '3.0L', entype: 'I6', isBookmarked: false, isFavorite: false },
                    { id: 4, name: 'BMW M3 Competition Touring', logo: '/images/Bmwmodel/bmwm3compt.png', class: 'bmwm3comptour',
                        power: '503HP', speed: '250+ km/h', encapacity: '3.0L', entype: 'I6', isBookmarked: false, isFavorite: false },
                    { id: 5, name: 'BMW M4 Coupe', logo: '/images/Bmwmodel/bmwm4coupe.png', class: 'bmwm4coupe',
                        power: '473HP', speed: '~250km/h', encapacity: '3.0L', entype: 'I6-V6 (Depending on modifications)', isBookmarked: false, isFavorite: false },
                    { id: 6, name: 'BMW M4 Convertible', logo: '/images/Bmwmodel/bmwm4conv.png', class: 'bmwm4conv',
                        power: '503HP', speed: '300km/h', encapacity: '3.2L', entype: 'I6', isBookmarked: false, isFavorite: false },
                    { id: 7, name: 'BMW M5 Sedan', logo: '/images/Bmwmodel/bmwm5sedan.png', class: 'bmwm5sed',
                        power: '600HP', speed: '305km/h', encapacity: '4.4L', entype: 'V-8', isBookmarked: false, isFavorite: false },
                    { id: 8, name: 'BMW M8 Coupe', logo: '/images/Bmwmodel/bmwm8coupe.png', class: 'bmwm8coupe',
                        power: '615HP', speed: '300km/h', encapacity: '4.4L', entype: 'V-8', isBookmarked: false, isFavorite: false },
                    { id: 9, name: 'BMW M8 Convertible', logo: '/images/Bmwmodel/bmwm8conv.png', class: 'bmwm8conv',
                        power: '615HP', speed: '300km/h', encapacity: '4.4L', entype: 'V-8', isBookmarked: false, isFavorite: false },
                    { id: 10, name: 'BMW M8 Gran Coupe', logo: '/images/Bmwmodel/bmwm8grcoupe.png', class: 'bmwm8grcoupe',
                        power: '615HP', speed: '280km/h', encapacity: '4.4L', entype: 'V-8', isBookmarked: false, isFavorite: false }
                ]
            },
            selectedSeria: null,
            numCards: 0
        }
    },
    methods: {
        selectSeria(series) {
            this.selectedSeria = series;
        },
        addBookmark(model) {
            if (model && 'isBookmarked' in model) {
                 const index = this.bookmarks.findIndex(el => el.name === model.name);
                    if (index === -1) {
                        this.bookmarks.push(model);
                            this.numCards++;
                    } else {
                        this.bookmarks.splice(index, 1);
                            this.numCards--;
                    }
                model.isBookmarked = !model.isBookmarked;
            } else {
                console.error('Model is undefined or does not have the property:', model)
            }
        },
        addFavorite(model) {
             if (model && 'isFavorite' in model) {
                model.isFavorite = !model.isFavorite;
            } else {
                console.error('Model is undefined or does not have the property isFavorite:', model);
            }
        },
        removeAllBookmark() {
            Object.values(this.models).forEach(series => {
                series.forEach(model => {
                    model.isBookmarked = false;
                    model.isFavorite = false;
                        this.bookmarks.splice(series, 1);
                        this.numCards = 0;
                });
            });
        }
    }
}
</script>