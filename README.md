for managing patch
Go to Firebase Console -> Remote Config -> Add Parameter (or "Create Configuration").

Host this .json file somewhere (GitHub Raw, Firebase Storage, S3).
Go to Firebase Console -> Remote Config.
Update flashcard_patch_url with the new link.
Update latest_flashcard_version to a higher number (e.g., 1.1).
Publish.
________________________________________________________________________________
1. The App Version (To trigger updates)
Parameter key: latest_app_version
Data type: String
Default value: 1.0.0
Usage: Whenever you release a new app version (e.g., to version 1.0.1), change this value to 1.0.1. Users on older versions will see the update popup.
2. Force Update (To lock the app for critical fixes)
Parameter key: force_update_required
Data type: Boolean
Default value: false
Usage: Set to true only if there is a critical bug and you want to prevent users from using the old app until they update. They won't be able to close the update dialog.
3. Store URL (Where the "Update" button goes)
Parameter key: update_store_url
Data type: String
Default value: https://play.google.com/store/apps/details?id=com.example.neetpgApp
Usage: Paste the actual link to your app on the Play Store here.
__________________________________________________________________________________
5. Announcement Message (The popup text)
Parameter key: general_announcement
Data type: String
Default value: (Leave empty)
Usage: Type your message here. For example: We will be performing server maintenance tonight from 2 AM to 4 AM. or New Pathology functionality added!
6. Announcement Title (The popup header)
Parameter key: announcement_title
Data type: String
Default value: 
Announcement
Usage: The bold title at the top of the dialog. You can change it to Maintenance Alert or New Feature.
7. Announcement ID (To ensure it shows only once)
Parameter key: announcement_id
Data type: String
Default value: (Leave empty)
Usage: This is the most important one for announcements.
If you want to show a message, give it a unique ID like maintenance_jan_02.
The app saves this ID on the user's phone.
To send a new message next week, change this ID to something new, like feature_update_feb. The app sees the ID has changed and shows the new message.
