# AppDelegateExtensions
使用通知和runtime-AOP的为AppDelegate瘦身方案

### 使用姿势
在你的AppDelegate中：
```objc
+ (void)load
{
    installAppDelegateExtensionsWithClass(self);
}
```

添加了以下这些Notification key

```objc
UIKIT_EXTERN NSNotificationName const UIApplicationWillFinishLaunchingNotification;
UIKIT_EXTERN NSNotificationName const UIApplicationDidRegisterUserNotificationSettingsNotification;
UIKIT_EXTERN NSNotificationName const UIApplicationDidRegisterForRemoteNotificationsNotification;
UIKIT_EXTERN NSNotificationName const UIApplicationDidFailToRegisterForRemoteNotificationsNotification;
UIKIT_EXTERN NSNotificationName const UIApplicationDidReceiveRemoteNotification  NS_DEPRECATED_IOS(3_0, 10_0, "Use UserNotifications Framework's -[UNUserNotificationCenterDelegate willPresentNotification:withCompletionHandler:] or -[UNUserNotificationCenterDelegate didReceiveNotificationResponse:withCompletionHandler:] for user visible notifications and -[UIApplicationDelegate application:didReceiveRemoteNotification:fetchCompletionHandler:] for silent remote notifications");
UIKIT_EXTERN NSNotificationName const UIApplicationDidReceiveLocalNotification NS_DEPRECATED_IOS(4_0, 10_0, "Use UserNotifications Framework's -[UNUserNotificationCenterDelegate willPresentNotification:withCompletionHandler:] or -[UNUserNotificationCenterDelegate didReceiveNotificationResponse:withCompletionHandler:]");
UIKIT_EXTERN NSNotificationName const UIApplicationHandleOpenURLNotification NS_DEPRECATED_IOS(2_0, 9_0, "Please use application:openURL:options:");
UIKIT_EXTERN NSNotificationName const UIApplicationOpenURLWithSourceApplicationNotification NS_DEPRECATED_IOS(2_0, 9_0, "Please use application:openURL:options:");
UIKIT_EXTERN NSNotificationName const UIApplicationOpenURLWithOptionsNotification;
UIKIT_EXTERN NSNotificationName const UIApplicationContinueUserActivityNotification;
UIKIT_EXTERN NSNotificationName const UIApplicationPerformActionForShortcutItemNotification;
UIKIT_EXTERN NSNotificationName const UIApplicationHandleWatchKitExtensionRequestNotification;
```

具体细节：http://www.jianshu.com/p/a926fd605b7a

代码中参考了BlocksKit和libextobjc的实现，感谢两位大神的精彩code
