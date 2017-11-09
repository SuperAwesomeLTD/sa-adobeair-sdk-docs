Examples
========

Simple example
--------------

The first example shows how you can add a banner ad in your app with just a
few lines of code.

.. code-block:: actionscript


    import tv.superawesome.sdk.publisher.*;

    public class Demo extends Sprite {

        var banner: SABannerAd = null;

        // initialization
        public function Demo () {
            super ();

            // create a new banner
            banner = new SABannerAd ();

            // setup the banner
            banner.disableParentalGate();
            banner.enableBumperPage();

            // add a callback
            banner.setCallback (function (placementId: int, evt: int) {

                // when the ad loads, play it directly
                if (evt == SAEvent.adLoaded) {
                    banner.play ();
                }
            });

            // start the loading process
            banner.load (30471);
        }
    }


Complex example
---------------

This example shows how you can add different types of ads and make them respond to
multiple callbacks.

.. code-block:: actionscript

    import tv.superawesome.sdk.publisher.*;

    public class Demo extends Sprite {

        var banner: SABannerAd = null;

        // initialization
        public function Demo () {
            super ();

            // create a new banner
            banner = new SABanner ();

            // setup the banner
            banner.enableParentalGate ();
            banner.disableBumperPage ();

            // and load it
            banner.load (30471);

            // setup the video
            SAVideoAd.disableParentalGate ();
            SAVideoAd.enableBumperPage();
            SAVideoAd.disableCloseButton ();

            // and load it
            SAVideoAd.load (30479);
            SAVideoAd.load (30480);
        }

        public void playBanner () {

            if (banner.hasAdAvailable ()) {
                banner.play ();
            }
        }

        public void playVideo1 () {

            if (SAVideoAd.hasAdAvailable (30479)) {

                // do some last minute setup
                SAVideoAd.setOrientationLandscape ();

                // and play
                SAVideoAd.play (30479);
            }
        }

        public void playVideo2 () {

            if (SAVideoAd.hasAdAvailable (30480)) {

                // do some last minute setup
                SAVideoAd.setOrientationAny ();

                // and play
                SAVideoAd.play (30480);
            }
        }
    }
