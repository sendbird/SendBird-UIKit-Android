# Change Log

### v2.0.2 (January 26, 2021) with Core SDK `v3.0.156`
* Added `setEmptyIcon(int resId)` in `ChannelFragment.Builder`, `ChannelListFragment.Builder`, and `OpenChannelFragment.Builder`.
* Added `setEmptyText(int resId)` in `ChannelFragment.Builder`, `ChannelListFragment.Builder`, and `OpenChannelFragment.Builder`.

### v2.0.1 (January 11, 2021) with Core SDK `v3.0.154`
* Added `showMediaSelectDialog()` in `ChannelFragment` and `OpenChannelFragment`.
* Added `takeCamera()`, `takePhoto()`, and `takeFile()` in `ChannelFragment` and `OpenChannelFragment`.
* Added `setUseInputLeftButton(boolean useInputLeftButton)` in `ChannelFragment.Builder` and `OpenChannelFragment.Builder`.
* Support image resizing and compression
    * Added `setUseImageCompression(boolean)` and `shouldUseImageCompression()` in `SendBirdUIKit`
    * Added `setCompressQuality(int)` and `getCompressQuality()` in `SendBirdUIKit`
    * Added `setResizingSize(Pair<Integer, Integer>)` and `getResizingSize()` in `SendBirdUIKit`
* Fix compile issue on gradle 4.1.1

### v2.0.0 (December 23, 2020) with Core SDK `v3.0.153`
* Added OpenChannel features.
    * Added `OpenChannelSettingsActivity`, `ParticipantsListActivity`.
    * Added `OpenChannelFragment`, `OpenChannelSettingsFragment` and `ParticipantsListFragment`.
    * Added `onBeforeUpdateOpenChannel(OpenChannelParams params)` in `CustomParamsHandler`.
    * Added `styles_overlay.xml`.
* Added `enum KeyboardDisplayType { Plane, Dialog }`.
    * Added `setKeyboardDisplayType(KeyboardDisplayType type)` in `ChannelFragment.Builder`.
    * Added `setKeyboardDisplayType(KeyboardDisplayType type)` in `OpenChannelFragment.Builder`.
* Improved stability.

### v1.2.5 (December 10, 2020) with Core SDK `v3.0.152`
* Add opened interfaces for loading dialog
    * Added `shouldShowLoadingDialog()` in `ChannelFragment`, `MemberListFragment`, `BannedListFragment`, `OperatorListFragment`, `ModerationFragment`, and `MutedMemberListFragment`.
    * Added `shouldDismissLoadingDialog()` in `ChannelFragment`, `MemberListFragment`, `BannedListFragment`, `OperatorListFragment`, `ModerationFragment`, and `MutedMemberListFragment`.
* Improved stability.

### v1.2.4 (November 17, 2020) with Core SDK `v3.0.150`
* Disabled android.enableJetifier

### v1.2.3 (October 19, 2020) with Core SDK `v3.0.149`
* Added `setUseHeaderRightButton(boolean)` in `ChannelSettingsFragment`, `CreateChannelFragment`, `InviteChannelFragment`, `PromoteOperatorsFragment`.
* Improved stability.

### v1.2.2 (September 17, 2020) with Core SDK `v3.0.145`
* Supported user profile.
    * Added `setUseDefaultUserProfile(boolean)` in `SendBirdUIKit`
    * Added `setCustomParamsHandler(CustomParamsHandler handler)` in `SendbirdUIKit`
    * Added `setOnProfileClickListener`, `setUseUserProfile` in `ChannelFragment`, `MemberListFragment`, `BannedListFragment`, `MutedMemberListFragment`, `OperatorListFragment`.

### v1.2.1 (September 10, 2020) with Core SDK `v3.0.144`
* Supported message group UI.
* Added `setUseMessageGroupUI` in `ChannelFragment`.

### v1.2.0 (August 27, 2020) with Core SDK `v3.0.142`
* Added operator features
    * Member managing (ban/unban, mute/unmute, promote/dismiss)
    * Moderation feature for the operator
    * Channel freezing/unfreezing
    * Channel creator will be the default operator
    * Added `ModerationActivity`, `BannedListActivity`, `OperatorListActivity`, `MutedMemberListActivity`, and `PromoteOperatorsActivity`.
    * Added `ModerationFragment`, `BannedListFragment`, `OperatorListFragment`, `MutedMemberListFragment`, and `PromoteOperatorsFragment`.
* Added GroupChannel type selector.
* Added `newIntentFromCustomActivity` on each activities on UIKit
* Added `setCreateButtonText(String text)` in `InviteChannelFragment.Builder`
* Added `setInvitedButtonText(String text)` in `CreateChannelFragment.Builder`
* Deprecated `setMemberSettingClickListener(View.OnClickListener listener)` in `ChannelSettingsFragment`.
* Removed button attributes (Replaced with the button attributes of each component.)
    * `sb_button_contained_style`
    * `sb_button_uncontained_style`
    * `sb_button_warning_style`
    * `sb_button_cancel_style`
    * `sb_icon_button_style`
* Removed button styles (Replaced with the button attributes of each component.)
    * `Widget.SendBird.Button`
    * `Widget.SendBird.Button.Contained`
    * `Widget.SendBird.Button.Uncontained`
    * `Widget.SendBird.Button.Alert`
    * `Widget.SendBird.Button.Cancel`
    * `Widget.SendBird.IconButton`

### v1.1.3 (August 13, 2020) with Core SDK `v3.0.139`
* Implement OG tag messages.
* Improved stability.

### v1.1.2 (July 22, 2020)
* The following functions have been opened to send custom data.
    * Added `newIntentFromCustomActivity()` in each UIKit Activity.
* Improved stability.

### v1.1.1 (July 16, 2020) with Core SDK `v3.0.138`
* The following functions have been opened to send custom data.
    * Added `onBeforeInviteUsers()` with `userIds` in `InviteChannelFragment`.
    * Added `inviteUser()` with `userIds` in `InviteChannelFragment`.
    * Added `onNewUserInvited()` in `InviteChannelFragment`.
    * Added `setInviteButtonText()` in `InviteChannelFragment`.
    * Added `setInviteButtonEnabled()` in `InviteChannelFragment`.
    * Added `setCreateButtonText()` in `CreateChannelFragment`.
    * Added `setCreateButtonEnabled()` in `CreateChannelFragment`.
    * Added `setMemberSettingClickListener()` with `onClickListener` in `ChannelSettingsFragment.Builder`.
* Improved stability.
    
### v1.1.0 (July 10, 2020) with Core SDK `v3.0.137`
* Supports reaction feature.
    * Added `EmojiManager` class.
    * Added `EmojiListAdapter` class.
    * Added `EmojiReactionListAdapter` class.
    * Added `EmojiReactionUserListAdapter` class.
    * Added `setEmojiReactionClickListener(OnEmojiReactionClickListener emojiReactionClickListener)` in `ChannelFragment.Builder`.
    * Added `setEmojiReactionLongClickListener(OnEmojiReactionLongClickListener emojiReactionLongClickListener)` in `ChannelFragment.Builder`.
    * Added `setEmojiReactionMoreButtonClickListener(OnItemClickListener<BaseMessage> emojiReactionMoreButtonClickListener)` in `ChannelFragment.Builder`.
* Improved stability.

### v1.0.5 (June 25, 2020) with Core SDK `v3.0.136`
* Added - Unknown type message
* Added `setGroupChannelListQuery()` in `ChannelListFragment.Builder`.
* Added `setMessageListParams()` in `ChannelFragment.Builder`.

### v1.0.4 (June 14, 2020) with Core SDK `v3.0.133`
* The following functions have been opened to send custom data.
    * Added `onBeforeSendUserMessage()` with `UserMessageParams` in `ChannelFragment`.
    * Added `onBeforeUpdateUserMessage()` with `UserMessageParams` in `ChannelFragment`.
    * Added `sendUserMessage()` with `UserMessageParams` in `ChannelFragment`.
    * Added `onBeforeSendFileMessage()` with `FileMessageParams` in `ChannelFragment`.
    * Added `sendFileMessage()` with `Uri` in `ChannelFragment`.
    * Added `updateUserMessage()` with `messageId` and `UserMessageParams` in `ChannelFragment`.
    * Added `deleteMessage()` in `ChannelFragment`.
    * Added `resendMessage()` in `ChannelFragment`.
    * Added `onBeforeCreateGroupChannel()` with `GroupChannelParams` in `CreateChannelFragment`.
    * Added `createGroupChannel()` with `GroupChannelParams` in `CreateChannelFragment`.
    * Added `onNewChannelCreated()` in `CreateChannelFragment`.
    * Added `onBeforeUpdateGroupChannel()` with `GroupChannelParams` in `ChannelSettingsFragment`.
    * Added `updateGroupChannel()` with `GroupChannelParams` in `ChannelSettingsFragment`.
    * Added `leaveChannel()` in `ChannelSettingsFragment`.
    * Added `leaveChannel()` in `ChannelListFragment`.
    * Added `setCustomChannelFragment()` in `ChannelFragment.Builder`.
    * Added `setCustomChannelListFragment()` in `ChannelListFragment.Builder`.
    * Added `setCustomInviteChannelFragment()` in `InviteChannelFragment.Builder`.
    * Added `setCustomChannelSettingsFragment()` in `ChannelSettingsFragment.Builder`.
    * Added `setCustomCreateChannelFragment()` in `CreateChannelFragment.Builder`.
    * Added `setCustomMemberListFragment()` in `MemberListFragment.Builder`.
    * Added `createChannelFragment()` with `channelUrl` in `ChannelActivity`.
    * Added `createChannelListFragment()`, `createRedirectChannelActivityIntent()` in `ChannelListActivity`.
    * Added `createInviteChannelFragment()` with `channelUrl` in `InviteChannelActivity`.
    * Added `createChannelSettingsFragment()` with `channelUrl` in `ChannelSettingsActivity`.
    * Added `createCreateChannelFragment()` in `CreateChannelActivity`.
    * Added `createMemberListFragment()` with `channelUrl` in `MemberListActivity`.

### v1.0.3 (May 29, 2020) with Core SDK `v3.0.132`
* Improved stability.

### v1.0.2 (May 14, 2020)
* Added - `SendBirdUIKit.setLogLevel(LogLevel level)`
* Added - `LogLevel` in `SendBirdUIKit`
  * `ALL`, `INFO`, `WARN`, `ERROR`.

### v1.0.1 (Apr 29, 2020) with Core SDK `v3.0.129`
* Added - UIKit version information to User-Agent
* Improved stability.

### v1.0.0 (Apr 1, 2020)
* First release.
