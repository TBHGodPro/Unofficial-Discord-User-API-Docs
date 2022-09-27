# Data Types
> The only `Data Types` documented here are types that either:
>
> - Were changed due to being a user and not a bot
> - Are very important
>
> All other types are supplied as links to [Official Discord Documentation](https://discord.com/developers/docs)

<br/><br/>
### User
| FIELD | TYPE | DESCRIPTION |
| ----- | ---- | ----------- |
| username | string | The User's username |
| public_flags | integer | The [flags](https://discord.com/developers/docs/resources/user#user-object-user-flags) for the User |
| id | Snowflake | The User's ID |
| discriminator | string (integer parsable) |  The User's discriminator |
| avatar_decoration? | null | Unkown | Unkown |
| avatar | string | The avatar ID for the User|
| bot? | boolean | Whether the User is a bot |
| system? | boolean | Whether the User is a system bot |

<br/><br/> Client User
EXTENDS [USER](#user) FIELDS

| FIELD | TYPE | DESCRIPTION |
| ----- | ---- | ----------- |
| verified | boolean | Whether the email on the account is verified |
| email | string | The account's Email |
| purchased_flags | integer | Unkown |
| premium | boolean | Whether the user has Discord Nitro or not |
| premium_type? | [Nitro Type](https://discord.com/developers/docs/resources/user#user-object-premium-types) | The level of Nitro the user has (Only shows if `premium` is true) |
| phone? | Phone Number | The accounts linked phone number (if any) |
| nsfw_allowed | boolean | Whether the account allows NSFW content |
| mobile | boolean | Unkown |
| desktop | boolean | Unkown |
| mfa_enabled | boolean | Whether the account has 2fa enabled |
| flags | integer | The [flags](https://discord.com/developers/docs/resources/user#user-object-user-flags) for the User |
| bio | string | The account bio |
| banner_color | string &#124; null | The color for the User's banner |
| banner | string &#124; null | The banner ID for the User |
| accent_color | string &#124; null | The accent color for the account |

<br/><br/>
### User Settings
!> NOTE: There may be many more fields for this, we are only documenting the ones we know.

!> NOTE: All values here are optional and may not show up.

| FIELD | TYPE |
| ----- | ---- |
| inline_attachment_media | boolean |
| activitiy_restricted_guild_ids | Array&lt;Unkown&gt;
| show_current_game | boolean |
| friend_source_flags | Object&lt;string: Unkown&gt; |
| view_nsfw_guilds | boolean |
| enable_tts_command | boolean |
| render_reactions | boolean |
| gif_auto_play | boolean |
| stream_notifications_enabled | boolean |
| animate_emoji | boolean |
| afk_timeout | integer |
| view_nsfw_commands | boolean |
| detect_platform_accounts | boolean |
| status | "online" &#124; "invisible" &#124; "offline" &#124; "idle" &#124; "dnd" |
| explicit_content_filter | integer |
| custom_status | string &#124; null |
| default_guilds_restricted | boolean |
| theme | "dark" &#124; "light" |
| allow_accessibility_detection | boolean |
| locale | [Locale](https://discord.com/developers/docs/reference#locales) |
| native_phone_integration_enabled | boolean |
| guild_positions | Array&lt;Snowflake&gt; |
| timezone_offset | integer |
| friend_discovery_flags | integer |
| contact_sync_enabled | boolean |
| disable_games_tab | boolean |
| guild_folders | Array&lt;<br/>&#01;&#01;&#01;&#01;{<br/>&#01;&#01;&#01;&#01;&#01;&#01;&#01;&#01;name?: string,<br/>&#01;&#01;&#01;&#01;&#01;&#01;&#01;&#01;id?: Snowflake,<br/>&#01;&#01;&#01;&#01;&#01;&#01;&#01;&#01;color?: string,<br/>&#01;&#01;&#01;&#01;&#01;&#01;&#01;&#01;guild_ids: Array&lt;Snowflake&gt;<br/>&#01;&#01;&#01;&#01;}<br/>&gt; |
| inline_embed_media | boolean |
| developer_mode | boolean |
| render_embeds | boolean |
| animate_stickers | integer |
| message_display_compact | boolean |
| convert_emoticons | boolean |
| passwordless | boolean |
| restricted_guilds | Array&lt;Unkown (Predicted Snowflake)&gt; |

<br/><br/>
### Connected Account
| FIELD | TYPE |
| ----- | ---- |
| visibility | integer |
| verified | boolean |
| type | string |
| two_way_link | boolean |
| show_activity | boolean |
| revoked | boolean |
| name | string |
| id | Snowflake &#124; string &#124; null |
| friend_sync | boolean |
| access_token? | string |

<br/><br/>
### Guild
| FIELD | TYPE | DESCRIPTION |
| ----- | ---- | ----------- |
| id | Snowflake | The Guild ID |
| name | string | The Guild Name |
| description | string &#124; null | The description for the Guild |
| icon | string &#124; null | The Guild Icon ID |
| banner | string &#124; null | The Guild Banner ID |
| afk_timeout | integer | Unkown |
| guild_scheduled_events | Array&lt;[Scheduled Event](https://discord.com/developers/docs/resources/guild-scheduled-event#guild-scheduled-event-object)&gt; | The scheduled events for the Guild |
| system_channel_flags | [System Channel Flags](https://discord.com/developers/docs/resources/guild#guild-object-system-channel-flags) | Unkown |
| features | Array&lt;[Guild Feature](https://discord.com/developers/docs/resources/guild#guild-object-guild-features)&gt; | The guild features for the Guild |
| mfa_level | [MFA Level](https://discord.com/developers/docs/resources/guild#guild-object-mfa-level) | Unkown |
| guild_hashes | Array&lt;Weird Stuff IDK&gt; | Unkown |
| roles | Array&lt;[Role](https://discord.com/developers/docs/topics/permissions#role-object)&gt; | The roles for the Guild |
| rules_channel_id | Snowflake &#124; null | The ID for the Guild Rules Channel |
| stickers | Array&lt;[Sticker](https://discord.com/developers/docs/resources/sticker#sticker-object)&gt; | The stickers for the guild |
| nsfw_level | [Guild NSFW Level](https://discord.com/developers/docs/resources/guild#guild-object-guild-nsfw-level) | The NSFW Level for the Guild |
| large | boolean | Whether the guild is considered `large` or not |
| preferred_locale | [Locale](https://discord.com/developers/docs/reference#locales) | The preferred locale for the Guild |
| premium_subscription_count | integer | The amount of boosts the server has |
| premium_tier | [Premium Tier](https://discord.com/developers/docs/resources/guild#guild-object-premium-tier) | The boost level of the server |
| member_count | integer | The amount of members the guild has |
| system_channel_id | Snowflake &#124; null | The ID for the Guild System Channel |
| hub_type | null &#124; Unkown | Unkown |
| joined_at | Timestamp | When the User joined the Guild |
| max_video_channel_users | integer | The maximum amount of people that can be in one video channel in the Guild |
| public_updates_channel_id | Snowflake &#124; null | The ID for the Guild Public Updates Channel |
| threads | Array&lt;Thread&gt; | The threads for the Guild `(ALL TESTS HAVE RETURNED AN EMPTY ARRAY)` |
| splash | string &#124; null | The ID for the Guild Splash Screen |
| emojis | Array&lt;[Emoji](https://discord.com/developers/docs/resources/emoji#emoji-object)&gt; | The emojis for the server |
| nsfw | boolean | Whether the Guild is an NSFW Guild or not |
| application_command_counts | Object&lt;string: integer&gt; | Unkown |
| verification_level | integer | The level of account verificiation required to join the Guild |
| discovery_splash | string &#124; null | The ID for the splash screen in the Discovery Page for the Guild |
| explicit_content_filter | integer | The level of content filter for the Guild |
| channels | Array&lt;[Channel](https://discord.com/developers/docs/resources/channel#channel-object)&gt; | The Channels for the Guild |
| owner_id | Snowflake | The User ID for the Owner of the Guild |
| vanity_url_code | string | The vanity url code for the Guild |
| application_id | null &#124; Unkown (predicted Snowflake) | Unkown |
| lazy | boolean | Whether the Guild was lazy loaded (used for large Guilds) |
| premium_progress_bar_enabled | boolean | Whether the server boost progress bar is shown |
| afk_channel_id | Snowflake &#124; null | The ID for the Guild AFK Channel |
| max_members | integer | The max members for the guild |
| default_message_notifications | integer | Unkown |
| stage_instances | Array&lt;Unkown (predicted Stage Instance)&gt; | Unkown |

<br/><br/>
### User Guild Settings
!> NOTE: There may be many more fields for this, we are only documenting the ones we know.

!> NOTE: All values here are optional and may not show up.

!> NOTE: Structure of Object is {
   version: integer,
   partial: boolean,
   entries: Array&lt;DATA BELOW&gt;
}

| FIELD | TYPE |
| ----- | ---- |
| version | integer |
| suppress_roles | boolean |
| suppress_everyone | boolean |
| notify_highlights | integer |
| muted | boolean |
| mute_scheduled_events | boolean |
| mute_config | null &#124; {<br/>&#01;&#01;&#01;&#01;selected_time_window: null &#124; integer &#124; -1,<br/>&#01;&#01;&#01;&#01;end_time: null &#124; integer<br/>} |
| mobile_push | boolean |
| message_notifications | integer |
| hide_muted_channels | boolean |
| guild_id | Snowflake &#124; null |
| flags | integer |
| channel_overrides | Array&lt;[Channel Override](#channel-override)&gt; |

<br/><br/>
### Session
| FIELD | TYPE | DESCRIPTION |
| ----- | ---- | ----------- |
| status | "online" &#124; "invisible" &#124; "offline" &#124; "dnd" &#124; "idle" | The client status for this session |
| session_id | string | The ID for the session |
| activities | Array&lt;[Activity](#activity)&gt; | The activities for this session |
| client_info | {<br/>&#01;&#01;&#01;&#01;version: integer,<br/>&#01;&#01;&#01;&#01;os: string,<br/>&#01;&#01;&#01;&#01;client: string<br/>} | The client info for this session |

<br/><br/>
### Relationship
| FIELD | TYPE | DESCRIPTION |
| ----- | ---- | ----------- |
| user_id | Snowflake | The ID of the User |
| type | [Relationship Type](https://discord.com/developers/docs/game-sdk/relationships#data-models-relationshiptype-enum) | The type of relationship |
| nickname | null &#124; (possible string) | Unkown |
| id | Snowflake | The relationship ID |

<br/><br/>
### Private Channel
| FIELD | TYPE | DESCRIPTION |
| ----- | ---- | ----------- |
| type | 1: DM<br/>3: GC | The type of the Private Channel |
| id | Snowflake | The ID of the Private Channel |
| last_message_id | Snowflake | The ID of the last message that was sent (most likely used for deciding whether to fetch messages again or not) |
| last_pin_timestamp | Timestamp | The Timestamp of the last time a Message was Pinned (most likely used for deciding whether to fetch pins again or not) |
| recipient_ids | Array&lt;Snowflake&gt; | The IDs of the Users in the Private Channel (Excluding the User itself) |

<br/><br/>
### Channel Override 
| FIELD | TYPE |
| ----- | ---- |
| muted | boolean |
| message_notifications | integer |
| collapsed | boolean |
| channel_id | Snowflake |
| mute_config | null &#124; {<br/>&#01;&#01;&#01;&#01;selected_time_window: null &#124; integer &#124; -1,<br/>&#01;&#01;&#01;&#01;end_time: null &#124; integer<br/>} |

<br/><br/>
### Activity
| FIELD | TYPE | DESCRIPTION (WITH ENUMS) |
| ----- | ---- | ------------------------|
| type | integer | The type of the activity: <br/><br/>0: App<br/>2: Unkown (Shown For Spotify)<br/>4: Custom Status<br/><br/>MANY POSSIBLY UNKOWN |
| created_at | Timestamp | The time that the activity started |
| id | string | The ID of the activity<br/>Possible Values:<br/><br/>ID<br/>"custom"<br/>"${string}:${number}" (Ex: "spotify:1")<br/><br/>MANY POSSIBLY UNKOWN |
| name | string | The name of the activity (Shown on the 1st Row of the activity) |
| details? | string | Shown on the 2nd Row of the activity
| state? | string | Shown on the 3rd Row of the activity (Acts as the text for Custom Statuses) |
| application_id? | string | The discord application id for the activity app |
| flags? | integer | The flags for the activity |
| session_id? | string | The session id for the activity |
| timestamps? | {<br/>&#01;&#01;&#01;&#01;start?: Timestamp,<br/>&#01;&#01;&#01;&#01;end?: Timestamp<br/>} | The relevant timestamps for the activity |
| assets? | Array&lt;Any&gt; | Contains fields which contain relevant information that can be used |
| buttons? | Array&lt;string&gt; | The buttons for the activity |
| party? | Object | The party information for the activity |

!> There are fields that are specific to certain activities and those are not documented here