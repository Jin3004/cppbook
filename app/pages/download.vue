<template>

    <div class="uk-section-primary tm-section-texture">

        <navbar class="uk-navbar-transparent"/>

        <div class="uk-section uk-flex uk-flex-middle uk-text-center" uk-height-viewport="offset-top: true">
            <div class="uk-width-1-1">
                <div class="uk-container">

                    <p class="uk-margin-large-bottom">
                        <canvas style="color: #fff" width="142" height="117" uk-svg src="./images/download.svg"></canvas>
                    </p>

                    <h1>ダウンロードいただきありがとうございます。</h1>

                    <p class="uk-margin-medium-bottom uk-text-large">ミスやわかりにくい点があればお伝えください。<br class="uk-visible@s"> GitHubでのプルリクエストも大歓迎です。</p>

                    <div class="uk-grid-medium uk-child-width-auto uk-flex-inline" uk-grid>
                        <div>
                            <a class="uk-button uk-button-primary tm-button-primary uk-button-large" href="https://twitter.com/intent/tweet?text=Jin%E3%81%8C%E4%BD%9C%E3%81%A3%E3%81%9FC%EF%BC%8B%EF%BC%8B%E3%82%92%E5%AD%A6%E3%81%B6%E3%82%B5%E3%82%A4%E3%83%88%E3%81%A7%E3%81%99%EF%BC%81&via=CPP_IS_GOD&related=CPP_IS_GOD" target="_blank">
                                <span class="uk-margin-small-right" uk-icon="icon: twitter"></span>
                                <span class="uk-text-middle">Share on Twitter</span>
                            </a>
                        </div>
                        <div>
                            <!---<a class="uk-button uk-button-primary tm-button-primary uk-button-large" href="https://www.facebook.com/sharer/sharer.php?u=https://getuikit.com" target="_blank">
                                <span class="uk-margin-small-right" uk-icon="icon: facebook"></span>
                                <span class="uk-text-middle">Post on Facebook</span>--->
                            </a>
                        </div>
                    </div>

                </div>
            </div>
        </div>

    </div>

</template>

<script>

    import {ajax} from 'uikit-util';

    export default {

        mounted() {

            ajax('assets/uikit/package.json', {responseType: 'json'}).then(({response}) =>
                setTimeout(() => location.href = `https://github.com/uikit/uikit/releases/download/v${response.version}/uikit-${response.version}.zip`, 100)
            );

        }
    };

</script>
