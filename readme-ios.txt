How to integrate AppyJump Ads into your application.

1. Download the SDK

The ready SDK Bundle can be found on the AppyJump Control Panel. Go to Publisher -> Integration. 

2. Add the AppyJump SDK to your Project

You need to add the AppyJump SDK into your iOS Project. Here's how to do it.

	Step 1 - Add AppyJump  Framework

First, unzip the AppyJump SDK ZIP archive. Then, Drag & Drop the AppyJump Framework (AppyJump .framework ) from the Finder into the Frameworks Folder in your Xcode project. (alternatively you can right-click on Frameworks in Xcode and use "Add Files to..." option). 

	Step 2 - Check the -ObjC Linker Flag
Make sure that under Project -> Build Settings -> Other Linker Flags you have "-ObjC" added to load objective-C code from libraries.

3. Request and Display Banner Ads

Import the AppyJump.h and UIKit.h header files 
Declare a AppyJumpBannerViewDelegate property 
Declare that your View Controller implements AppyJumpBannerViewDelegate 
Add the following lines of code in your View Controller's .h File

#import <UIKit/UIKit.h>
#import <AppyJump/AppyJump.h>
@interface ViewController : UIViewController <AppyJumpBannerViewDelegate>
In your .m file remember to @synthesize bannerView. Additionally:

- (NSString *)publisherIdForAppyJumpBannerView:(AppyJumpBannerView *)banner
{
    NSLog(@"This is publish id");
    return @"ENTER_YOUR_PUBLISHER_ID_HERE";
}

Set any Custom Parameters and Display the Ad using the following code:

 AppyJumpBannerView *bannerView = [[AppyJumpBannerView alloc] initWithFrame:CGRectZero]; // size does not matter yet
    bannerView.delegate = self;  // triggers ad loading
    bannerView.backgroundColor = [UIColor darkGrayColor]; // fill horizontally
    bannerView.refreshAnimation = UIViewAnimationTransitionCurlDown;
    [self.view addSubview:bannerView];
Available Methods and Callbacks for Banner Ads

- (void)AppyJumpBannerViewDidLoadAppyJumpAd:(AppyJumpBannerView *)banner
- (void)AppyJumpBannerView:(AppyJumpBannerView *)banner didFailToReceiveAdWithError:(NSError *)error
- (NSString *)publisherIdForAppyJumpBannerView:(AppyJumpBannerView *)banner



For more reference, please see also Demo App

