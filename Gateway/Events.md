# Gateway Events

Gateway events are dispatched with the [Opcode 0 Dispatch Event](/Gateway/Opcodes.md?id=_0-dispatch-event)

### READY

Recieved when the client has successfully authenticated using the [Opcode 2 Identify](/Gateway/Opcodes.md?id=_2-identify).

| FIELD                   | TYPE                                                      | DESCRIPTION                                                                                                                                    |
| ----------------------- | --------------------------------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------- |
| v                       | integer                                                   | API Version                                                                                                                                    |
| users                   | Array<[User](/Data-Types#user)>                           | Data for a bunch of users you're client will need to have (mostly friends, blocked users, friend requests, etc..)                              |
| user_settings_proto     | string                                                    | Unkown                                                                                                                                         |
| user_settings           | [User Settings](/Data-Types#user-settings)                | HUGE Amount of the User's settings                                                                                                             |
| user_guild_settings     | [User Guild Settings](/Data-Types#user-guild-settings)    | Settings for each of the User's guilds                                                                                                         |
| user                    | [Client User](/Data-Types#client-user)                    | The user for the client, which is just like a normal user but with more information                                                            |
| tutorial                | Unkown (nullable)                                         | Unkown                                                                                                                                         |
| sessions                | Array<[Session](/Data-Types#session)>                     | The sessions for the user                                                                                                                      |
| session_type            | string ("normal")                                         | Unkown                                                                                                                                         |
| session_id              | string                                                    | The ID for the session which you can use in [Opcode 6 Resume](/Gateway/Opcodes#6-resume)s                                                      |
| resume_gateway_url      | string                                                    | The URL to use for reconnecting in [Opcoed 6 Resume](/Gateway/Opcodes#6-resume)s                                                               |
| relationships           | Array<[Relationship](/Data-Types#relationship)>           | The User's Relationships (Friends, Blocked Users, Friend Requests, etc..) (Mapped to IDs)                                                      |
| read_state              | Object<string: Unkown>                                    | Unkown                                                                                                                                         |
| private_channels        | Array<[Private Channel](/Data-Types#private-channel)>     | The User's Private Channels                                                                                                                    |
| merged_members          | Array&lt;Unkown&gt;                                       | Unkown                                                                                                                                         |
| guilds                  | Array<[Guild](/Data-Types#guild)>                         | The Guilds the user is in                                                                                                                      |
| guild_join_requests     | Unkown                                                    | Unkown                                                                                                                                         |
| guild_experiments       | Array&lt;Unkown&gt;                                       | Unkown                                                                                                                                         |
| geo_ordered_rtc_regions | Array&lt;string&gt;                                       | The RTC Regions that are recommended for this User                                                                                             |
| friend_suggestion_count | integer                                                   | Unkown                                                                                                                                         |
| experiments             | Array&lt;Unkown&gt;                                       | Unkown                                                                                                                                         |
| country_code            | string                                                    | The country code for this User's country                                                                                                       |
| consents                | Object&lt;string: Unkown&gt;                              | Unkown                                                                                                                                         |
| connected_accounts      | Array<[Connected Account](/Data-Types#connected-account)> | The connected accounts for this User                                                                                                           |
| auth_session_id_hash    | string                                                    | Unkown                                                                                                                                         |
| analytics_token         | string                                                    | The analytics token for Discord (Should not be used because the format for analytics messages is unkown and it might get your account flagged) |
| \_trace                 | Stringified Array&lt;Any&gt;                              | Unkown                                                                                                                                         |
