App Wall
========

The following code block sets up a App Wall and loads it:

.. code-block:: actionscript

    public class Demo extends Sprite {

        // initialization
        public function Demo () {
            super ();

            // to display test ads
            SAAppWall.enableTestMode ();

            // ask users to add two numbers when clicking on an ad
            SAAppWall.enableParentalGate ();

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

These are default values for all the parameters:

================== =============
Parameter          Value
================== =============
Configuration 	   Production
Test mode          Disabled
Parental gate      Enabled
================== =============
