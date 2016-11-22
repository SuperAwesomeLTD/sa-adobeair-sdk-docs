Handle CPI
==========

You can install and use the SuperAwesome SDK as an advertiser as well, if you want to measure your CPI (Cost per Install)
performance.

For Android builds, all you have to do is make sure that the following receiver is registered in your Manifest Additions file:

.. code-block:: shell

    <receiver android:name="tv.superawesome.sdk.cpi.SACPI" android:exported="true">
        <intent-filter><action android:name="com.android.vending.INSTALL_REFERRER"/></intent-filter>
    </receiver>

For iOS builds, you'll have to add this to one of your classes:

.. code-block:: actionscript

    public class Demo extends Sprite {

      public function Demo () {
        super ();

        // this will send the necessary CPI events
        SuperAwesome.getInstance ().handleCPI ();
      }
    }
