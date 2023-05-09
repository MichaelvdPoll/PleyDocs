## Notifications

Code snippets reference incorrect namespace

```cs
// Schedule notifications
// Remember to initialize the SDK first.
using Trail;

//Notification will be delivered in 10 minutes
var delay = TimeSpan.FromSeconds(600);

// Image paths are relative to the 'StreamingAssets'-folder
var imagePath = "notification_image.png";
var iconPath = "notification_icon.png";

Trail.NotificationsKit.ScheduleLocalNotification("Notification title", "Notification body", imagePath, iconPath, delay,
    (result, notificationId) => {
        if (result.IsOk())
        {
            Debug.Log($"Successfully scheduled notification in {delay} seconds: {notificationId}");
        }
        else
        {
            Debug.LogError($"Failed to schedule notification in {delay} seconds: {result}");
        }
});

```

```cs
// Remember to initialize the SDK first.
using Trail;

// Cancel specific notification by Notification ID
Trail.NotificationsKit.CancelScheduledNotification(notificationId);

// Cancel all notifications
Trail.NotificationsKit.CancelAllScheduledNotifications();

```