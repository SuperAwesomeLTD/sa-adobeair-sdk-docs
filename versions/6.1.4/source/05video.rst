Video Ads
=========

The following code block sets up a video ad and loads it:

.. code-block:: actionscript

    public class Demo extends Sprite {

        // initialization
        public function Demo () {
            super ();

            // set config to production
            SAVideoAd.setConfigurationProduction ();

            // to display test ads
            SAVideoAd.enableTestMode ();

            // lock orientation to portrait or landscape
            SAVideoAd.setOrientationPortrait ();

            // enable or disable a close button
            SAVideoAd.enableCloseButton ();

            // enable or disable the android back button
            SAVideoAd.enableBackButton ();

            // enable or disable auto-closing at the end
            SAVideoAd.disableCloseAtEnd ();

            // clicks on the whole video surface
            SAVideoAd.disableSmallClick ();

            // start loading ad data for a placement
            SAVideoAd.load (30479);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: actionscript

    public void playVideo () {

        // check if ad is loaded
        if (SAVideoAd.hasAdAvailable (30479)) {

            // display the ad
            SAVideoAd.play (30479);
        }
    }

These are the default values:

================== =============
Parameter          Value
================== =============
Configuration 	   Production
Test mode          Disabled
Orientation        Any
Closes at end      True
Close button       Disabled
Small click button Disabled
Back button				 Enabled
================== =============

.. note:: For iOS, when locking orientation with either the **setOrientationPortrait** or **setOrientationLandscape** methods, the SDK will first look at the list of orientations
          supported by your app and conform to that.
          If, for example, you set a video ad to display in landscape mode but your app only supports portrait orientations, the ad will show in portrait mode.
          There are no such restrictions for Android.
