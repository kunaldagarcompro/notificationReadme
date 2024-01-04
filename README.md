# Production
npm start

# Development
npm run start:dev

# Launch Type
The notification component has 2 launchType way two launch app
1. Component: (for production) component run in other apps only
2. App : (for development) component run in other apps + index html hosted for testing.

# Setting Up
To run notifications app you need to import its css and js and then from respective UMD module create the instance using constructor.

## Announcement
UMD module = AnnouncementComponent
```
<script>
        var nVersion = Date.now();
        (function() {
                var preloadAnnouncement = document.createElement('link');
                preloadAnnouncement.href = '/notifications/js/announcement-component.js?v=' + nVersion;
                preloadAnnouncement.as = "script";
                document.head.appendChild(preloadAnnouncement);

                var preloadAnnouncement = document.createElement('link');
                preloadAnnouncement.href = '/notifications/css/announcement-component-styles.css?v=' + nVersion;
                preloadAnnouncement.as = "style";
                document.head.appendChild(preloadAnnouncement);
        })();
    </script>
```

## Notification
UMD module = NotificationComponent
```
<script>
        var nVersion = Date.now();
        (function() {
                var preloadNotification = document.createElement('link');
                preloadNotification.href = '/notifications/js/notification-component.js?v=' + nVersion;
                preloadNotification.rel = "preload";
                preloadNotification.as = "script";
                document.head.appendChild(preloadNotification);

                var preloadNotification = document.createElement('link');
                preloadNotification.href = '/notifications/css/notification-component-styles.css?v=' + nVersion;
                preloadNotification.rel = "preload";
                preloadNotification.as = "style";
                document.head.appendChild(preloadNotification);
        })();
    </script>
```

## Both (Announcement and Notification)
UMD module = NotificationsComponent
```
<script>
        var nVersion = Date.now();
        (function() {
                var preloadNotifications = document.createElement('link');
                preloadNotifications.href = '/notifications/js/notifications-component.js?v=' + nVersion;
                preloadNotifications.rel = "preload";
                preloadNotifications.as = "script";
                document.head.appendChild(preloadNotifications);

                var preloadNotifications = document.createElement('link');
                preloadNotifications.href = '/notifications/css/notifications-component-styles.css?v=' + nVersion;
                preloadNotifications.rel = "preload";
                preloadNotifications.as = "style";
                document.head.appendChild(preloadNotifications);
        })();
    </script>
```




