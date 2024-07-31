<template>
    <div class="main-container">
        <ul class="sidebar-list">
            <li title="Bookmarks" @click="showBookmarks">
                <div class="icon-content">
                    <div class="icon-bookmarks icon">
                        <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" fill="#fff" class="bi bi-bookmark-fill" viewBox="0 0 16 16">
                            <path d="M2 2v13.5a.5.5 0 0 0 .74.439L8 13.069l5.26 2.87A.5.5 0 0 0 14 15.5V2a2 2 0 0 0-2-2H4a2 2 0 0 0-2 2"/>
                        </svg>
                    </div>
                    <span v-if="bookmarks.length > 0 && showMessage" class="message-label"> {{ bookmarks.length }} </span>
                        <span class="hidden-title bookmarks">Bookmarks</span>
                </div>
            </li>
            <li title="Clear bookmarks" @click="delBookmarks">
                <div class="icon-content">
                    <div class="icon-rem icon">
                        <svg xmlns="http://www.w3.org/2000/svg" width="28" height="28" fill="#ff0000" class="bi bi-bookmark-x-fill " viewBox="0 0 16 16">
                            <path fill-rule="evenodd" d="M2 15.5V2a2 2 0 0 1 2-2h8a2 2 0 0 1 2 2v13.5a.5.5 0 0 1-.74.439L8 13.069l-5.26 2.87A.5.5 0 0 1 2 15.5M6.854 5.146a.5.5 0 1 0-.708.708L7.293 7 6.146 8.146a.5.5 0 1 0 .708.708L8 7.707l1.146 1.147a.5.5 0 1 0 .708-.708L8.707 7l1.147-1.146a.5.5 0 0 0-.708-.708L8 6.293z"/>
                        </svg>
                    </div>
                        <span class="hidden-title remove">Remove all</span>
                </div>
            </li>
        </ul>
        <div class="bookmark-container" v-if="visBookmark">
             <Bookmark 
                :bookmarks="bookmarks"
                :numCards="numCards"
                @close-at-bookmark="handleCloseBookmark"
            />
        </div>
    </div>
</template>

<style scoped>

    .bookmark-container {
        position: fixed;
        display: flex;
        align-items: center;
        justify-content: center;
        z-index: 1000;
        width: 100%;
        height: 100%;
        top: 0;
        left: 0;
        background-color: #0c152195;
        overflow: hidden;
    }

    .sidebar-list {
        padding: 20px;
        background: linear-gradient(45deg, rgb(37, 75, 173), rgb(16, 28, 96));
        box-shadow: 0 0 20px #000;
        width: 30px;
        height: 350px;
        margin-left: 20px;
        border-radius: 10px 0 0 10px;
        list-style-type: none;
        display: flex;
        flex-direction: column;
        justify-content: space-evenly;
        transition: padding 0.3s ease, box-shadow 0.4s ease;
    }

    .sidebar-list:hover {
        padding-right: 100px;
        cursor: pointer;
        box-shadow: 0 0 30px #000000;
    }

    .sidebar-list .message-label {
        content: '';
        position: absolute;
        background-color: red;
        display: block;
        align-content: center;
        z-index: 700;
        width: 10px;
        height: 10px;
        border-radius: 50%;
        right: 0;
        top: -3px;
        color: #fff;
        font-size: 8px;
        font-weight: 700;
        text-align: center;
    }

    .sidebar-list:hover .hidden-title {
        opacity: 1;
    }

    .sidebar-list li {
        position: relative;
        display: flex;
        flex-direction: row;
    }

    .sidebar-list .icon-content {
        display: flex;
        align-items: center;
        gap: 5px;
        transition: all 0.2s ease;
    }

    .sidebar-list .hidden-title {
        transition: opacity 0.2s ease-in-out;
        font-family: 'Lato', sans-serif;
        position: absolute;
        top: 5px;
        right: -95px;
        width: 90px;
        font-weight: 600;
        font-size: 17px;
        opacity: 0;
    }

    .sidebar-list .icon-content .icon {
        transition: all 0.2s ease;
    }

    .sidebar-list .bookmarks {
        color: aliceblue;
    }

    .sidebar-list .remove {
        color: rgb(255, 54, 54);
    }

    .sidebar-list .icon-bookmarks:hover {
        transform: scale(1.1);
        filter: drop-shadow(0 0 10px #ffffff89);
    }

    .sidebar-list .icon-rem:hover {
        transform: scale(1.1);
        filter: drop-shadow(0 0 15px #ff0000);
    }

    @media (max-width: 1330px) {
        .main-container {
            display: flex;
            flex-direction: row;
            width: 100%;
            justify-content: center;
        }
        .main-container .sidebar-list {
            margin: 0;
            flex-direction: row;
            border-radius: none;
            width: 100%;
            height: 30px;
        }
        .sidebar-list:hover {
            padding-right: 0;
        }
    }

</style>

<script>
import Bookmark from './Bookmark.vue';

export default {
    name: 'SideBar',
    components: {
      Bookmark  
    },
    props: {
        bookmarks: {
            type: Array,
            required: true
        },
        numCards: {
            type: Number,
            required: true
        }
    },
    data() {
        return {
            visBookmark: false,
            showMessage: true,
        }
    },
    methods: {
        showBookmarks() {
            this.visBookmark = !this.visBookmark;
            this.showMessage = false
        },
        delBookmarks() {
            this.$emit('remove-bookmark');
        },
        handleCloseBookmark() {
            this.visBookmark = false
        }
    }
}
</script>