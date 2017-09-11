App Wall
========

The following code block sets up a App Wall and loads it:

.. code-block:: actionscript

    public class Demo extends Sprite {

        // initialization
        public function Demo () {
            super ();

            // configure production
            SAAppWall.setConfigurationProduction ();

            // to display test ads
            SAAppWall.enableTestMode ();

            // enable or disable the android back button
            SAAppWall.enableBackButton ();

            // start loading ad data for a placement
            SAAppWall.load (88888);
        }
    }

Once you've loaded an ad, you can also display it:

.. code-block:: actionscript

    public void playInterstitial () {

        // check if ad is loaded
        if (SAAppWall.hasAdAvailable (88888)) {

            // display the ad
            SAAppWall.play (88888);
        }
    }

These are the default values:

================== =============
Parameter          Value
================== =============
Configuration 	   Production
Test mode          Disabled
Back button				 Enabled
================== =============
