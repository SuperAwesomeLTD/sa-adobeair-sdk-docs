Handle CPI
==========

You can install and use the SuperAwesome SDK as an advertiser as well, if you want to measure your CPI (Cost per Install)
performance.

The first step you have to do is make sure that the following receiver is registered in your ApplicationManifest.xml file (and it should be automatically added by the
SuperAwesome SDK when you build to Android):

.. code-block:: shell

    <receiver android:name="tv.superawesome.sdk.cpi.SACPI"
              android:exported="false"
              android:permission="tv.superawesome.sdk.SuperAwesomeSDK">
              <intent-filter>
                <action android:name="com.android.vending.INSTALL_REFERRER"/>
              </intent-filter>
    </receiver>

		Secondly, when the app first starts, make sure you have the following code added:

.. code-block:: actionscript

    public class Demo extends Sprite {

      public function Demo () {
        super ();

        // this will send the necessary CPI events
        SuperAwesome.getInstance ().handleCPI (function (success: Boolean): void {
          // this callback method will indicate if the AwesomeAds server
          // considered the install event you sent a success or not
        });
      }
    }
