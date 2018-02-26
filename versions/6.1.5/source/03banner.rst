Banner Ads
==========

The following block of code creates and loads a banner ad:

.. code-block:: actionscript

    public class Demo extends Sprite {

        var banner: SABannerAd = null;

        public function Demo () {
            super ();

            // create a new banner
            banner = new SABannerAd();

            // set production mode
            banner.setConfigurationProduction ();

            // switch test mode
            banner.enableTestMode ();

            // start loading ad data for a placement
            banner.load (30471);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: actionscript

    public void onClick () {

        // check if ad is loaded
        if (banner.hasAdAvailable ()) {

            // set a size template
            banner.setSize_320_50 ();

            // set a background color
            banner.setColorGray ();

            // choose between top or bottom
            banner.setPositionTop ();

            // display the ad
            banner.play ();
        }
    }

These are the default values:

============= =============
Parameter     Value
============= =============
Configuration Production
Test mode     Disabled
Background    Gray
Size          320x50
Position			Bottom
============= =============
