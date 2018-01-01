
How to integrate AppyJump Ads into your application.

1. Download the SDK

The ready SDK Bundle can be found on AppyJump control panel, under Publisher -> Integration. 

2. Add the AppyJump SDK to your Project

Before you can start integrating the actual ad units, you have to add the AppyJump SDK into your Android Project. Here's how to do it.

	a. Add the AppyJump SDK	

Unzip the SDK File and copy the AppyJump SDK to your project.

	b. Add Permissions:

     Declare the following permissions in your AndroidManifest.xml file: 

	<!-- Add permission for AppyJump Ads -->
    <uses-permission android:name="android.permission.INTERNET" />
	

	c. Add Activities:

	Declare the following activities in your AndroidManifest.xml file: 

	<!--  Activity for banner and Interstitial Ads -->
	<activity
		android:name="com.appyjump.sdk.InAppWebView"
		android:configChanges="keyboardHidden|orientation|screenSize"/>
	
	<!-- activity for Interstitial Ads -->
	<activity
		android:name="com.appyjump.sdk.Interstitial"
		android:configChanges="keyboardHidden|orientation|screenSize"/>


   
3. Request and Display Banner Ads


	AppyjumpAds appyjumpAds=new AppyjumpAds(Context context, String publisherId, String adType);
        appyjumpAds.show();
	
	There are two types of Ads parameter: AppyjumpAds.BANNER for banner Ads and AppyjumpAds.INTERSTITIAL for Interstitial Ads.

	
 	