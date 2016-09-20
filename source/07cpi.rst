Handle CPI
==========

You can install and use the SuperAwesome SDK as an advertiser as well, if you want to measure your CPI (Cost per Install)
performance.

All you have to do is make sure that the following receiver is registered in your Manifest Additions file:

.. code-block:: shell

    <receiver android:name="tv.superawesome.sdk.cpi.SACPI" android:exported="true">
        <intent-filter><action android:name="com.android.vending.INSTALL_REFERRER"/></intent-filter>
    </receiver>
