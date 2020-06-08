## Change Log

### v1.0.4 (May 14, 2020) with Core SDK `v3.0.133`
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
