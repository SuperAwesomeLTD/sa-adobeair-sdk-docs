Interstitial Ads
================

The following code block sets up an interstitial ad and loads it:

.. code-block:: actionscript

    public class Demo extends Sprite {

        // initialization
        public function Demo () {
            super ();

            // to display test ads
            SAInterstitialAd.enableTestMode ();

            // set config to production
            SAInterstitialAd.setConfigurationProduction ();

            // lock orientation to portrait or landscape
            SAInterstitialAd.setOrientationPortrait ();

            // enable or disable the android back button
            SAInterstitialAd.enableBackButton ();

            // start loading ad data for a placement
            SAInterstitialAd.load (30473);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: actionscript

    public void playInterstitial () {

        // check if ad is loaded
        if (SAInterstitialAd.hasAdAvailable (30473)) {

            // display the ad
            SAInterstitialAd.play (30473);
        }
    }

These are the default values:

============= =============
Parameter     Value
============= =============
Configuration Production
Test mode     Disabled
Orientation   Any
Back button   Enabled
============= =============

.. note:: For iOS, when locking orientation with either the **setOrientationPortrait** or **setOrientationLandscape** methods, the SDK will first look at the list of orientations
          supported by your app and conform to that.
          If, for example, you set an interstitial ad to display in landscape mode but your app only supports portrait orientations, the ad will show in portrait mode.
					There are no such restrictions for Android.
