# ![LOGO](logo.png) IoE² IoT API - to create end-user applications **flow**ground Connector

## Description

A generated **flow**ground connector for the IoE² IoT API - to create end-user applications API (version 3.0.0).

Generated from: https://api.apis.guru/v2/specs/ijenko.net/3.0.0/swagger.json<br/>
Generated at: 2019-05-07T17:42:22+03:00

## API Description



## Authorization

Supported authorization schemes:
- API Key- API Key
## Actions

### Change the password

> Set a new password for the account.<br/>
> <br/>
> **Note**: requires full access to the *Account*.

*Tags:* `Account`

### List Places of the Account

> List the *Places* of the account.<br/>
> <br/>
> **Note:** requires full access to the *Account*.

*Tags:* `Account`

### Create a Place

> Create a new *Place*.<br/>
> <br/>
> A *Device* (`class`: `MINT`, `address`: `0`) is automatically created and attached to the new *Place*.<br/>
> <br/>
> **Note:** requires full access to the *Account*.

*Tags:* `Account`

### List active Tokens of the Account

> List the active *Tokens* on the account.<br/>
> <br/>
> **Note:** requires full access to the *Account*.

*Tags:* `Account`

### Revoke a Token

> Revoke the given *Token*.<br/>
> <br/>
> **Note:** requires full access to the *Account*.

*Tags:* `Account`

#### Input Parameters
* `tokenId` - _required_ - Identifier of the token

### List Users of the Account

> Get the list of *Users* of this *Account*.

*Tags:* `Account`

#### Input Parameters
* `embed-metadata` - _optional_ - Request to include the given keys of metadata in the response. If a key doesn't exist on the resource it is ignored.
**Note:** This only applies to the top level resources.


### New User

> Add a *User*.<br/>
> <br/>
> **Note**: requires full access to the *Account*.

*Tags:* `Account`

### Delete a User

> Delete a *User* from this *Account*, and revoke all his/her *Tokens*.<br/>
> <br/>
> **Note**: requires full access to the *Account*.

*Tags:* `Account`

#### Input Parameters
* `userId` - _required_ - Unique identifier of a *User*.

### Information about a User

> Get information about a *User* in the same *Account*.

*Tags:* `Account`

#### Input Parameters
* `userId` - _required_ - Unique identifier of a *User*.

### Modify a User

> Modify a *User*.<br/>
> <br/>
> **Note**: requires full access to the *Account*.

*Tags:* `Account`

#### Input Parameters
* `userId` - _required_ - Unique identifier of a *User*.

### List metadata

> Get the metadata.

*Tags:* `Account`

#### Input Parameters
* `userId` - _required_ - Unique identifier of a *User*.

### Modify metadata

> Modify the metadata.<br/>
> Keys are limited to the same format as tags (up to 21 characters, [a-z0-9], starting with [a-z]). Values can be any JSON value.

*Tags:* `Account`

#### Input Parameters
* `userId` - _required_ - Unique identifier of a *User*.

### Get a token using login+password

> Get an access+refresh tokens pair from login and password information.<br/>
> <br/>
> The *access token* obtained with this request can then be used in<br/>
> an `Access-Token` HTTP header or in a `token` URL query parameter<br/>
> in requests that require authentication.<br/>
> <br/>
> The *refresh token* can be used with `/auth/refresh` when the *access<br/>
> token* expires to retrieve a new *access token*. The lifetime of the<br/>
> refresh token is the maximum lifetime of this authentication request.<br/>
> <br/>
> The default lifetime of the *refresh token* is defined by the `appId`<br/>
> used. The `ttl` input parameter allows to request a *refresh token*<br/>
> with a shorter lifetime.<br/>
> <br/>
> To implement *logout*, use `/auth/revoke`.

*Tags:* `Authentication` `Entry points`

### Refresh a token

> Get a new *access token* using a valid *refresh token*.<br/>
> <br/>
> This is a **replacement** of the *access token*: if an existing *access<br/>
> token* was still not expired, it is invalidated.

*Tags:* `Authentication`

### Ask for a new password

> Trigger the request of a new password.<br/>
> <br/>
> The account administrator will receive an e-mail with an URL pointing to a form<br/>
> to allow him/her to enter a new password.<br/>
> The old password is still functional until a new one is submitted.<br/>
> <br/>
> Either the login or e-mail of the account must be given.

*Tags:* `Authentication`

### Revoke a token

> Invalidate the authentication used for the request. The access token and the refresh token will be invalid after this request.<br/>
> This request is typically called to implement logout.

*Tags:* `Authentication`

### Information about a Device

> Get information about a *Device*.

*Tags:* `Device`

#### Input Parameters
* `deviceId` - _required_ - Unique identifier of a *Device*.

### Update a Device

> Modify information about a *Device*: its name.

*Tags:* `Device`

#### Input Parameters
* `deviceId` - _required_ - Unique identifier of a *Device*.

### Add dynamically a functionality

> Add a *Functionality* to the device.<br/>
> <br/>
> Required parameters are :<br/>
> - functionality class<br/>
> - endpoint<br/>
> <br/>
> Each device class has its own restrictions on which Functionality classes can be added and on which endpoints.<br/>
> Only a few devices allow to add Functionalities.<br/>
> <br/>
> |Device class|Functionality class|Endpoints|<br/>
> |------------|-------------------|---------|<br/>
> |MINT        |CurrentPeriod      |1,2,3    |<br/>
> |MINT        |ElectricityRates   |1,2,3    |<br/>
> |MINT        |GenericRate        |1,2,3    |<br/>
> <br/>
> **Note**: requires full access to the *Account*.

*Tags:* `Device` `Functionality`

#### Input Parameters
* `deviceId` - _required_ - Unique identifier of a *Device*.

### List metadata

> Get the metadata.

*Tags:* `Device`

#### Input Parameters
* `deviceId` - _required_ - Unique identifier of a *Device*.

### Modify metadata

> Modify the metadata.<br/>
> Keys are limited to the same format as tags (up to 21 characters, [a-z0-9], starting with [a-z]). Values can be any JSON value.

*Tags:* `Device`

#### Input Parameters
* `deviceId` - _required_ - Unique identifier of a *Device*.

### Run actions

> Run an *Action* on zero, one or multiple Functionalities selected with tags.

*Tags:* `Action`

#### Input Parameters
* `deviceId` - _required_ - Unique identifier of a *Device*.
* `action` - _required_ - Identifier of an *Action* inside a *Functionality*.
* `functionalities` - _required_ - Functionality selector: Functionality tags or functionality class (optionally, '@' followed by a endpoint in decimal) or '*' for all. Multiple values are separated by '|' and are interpreted as << OR >>.


### List tags

> Get the tags of a *Device*.

*Tags:* `Device`

#### Input Parameters
* `deviceId` - _required_ - Unique identifier of a *Device*.

### Modify tags

> Modify the tags of a *Device*.

*Tags:* `Device`

#### Input Parameters
* `deviceId` - _required_ - Unique identifier of a *Device*.

### Information about a Functionality

> Get the *Functionality*.

*Tags:* `Functionality`

#### Input Parameters
* `functionalityId` - _required_ - Unique identifier of a *Functionality*.

### Modify a Functionality

> Modify information about a *Functionality*: its name.

*Tags:* `Functionality`

#### Input Parameters
* `functionalityId` - _required_ - Unique identifier of a *Functionality*.

### Get history of multiple attributes

> Get the values of multiple *Attributes* and their history.<br/>
> <br/>
> If the `names` parameter is not given, all the attributes of the *Functionality*<br/>
> are returned. As the list may be huge, this must be avoided.<br/>
> <br/>
> If the `to` parameter is set, `from` must also be set.<br/>
> <br/>
> If `from` is not set, only the last value is returned.<br/>
> <br/>
> The `surround` parameter allows to ask also for one value beyond each interval boundaries.<br/>
> <br/>
> The request may fail if too many values are asked.

*Tags:* `Functionality`

#### Input Parameters
* `names` - _optional_ - One or multiple *Attribute* names separated by commas
* `from` - _optional_ - Beginning of the time interval.
* `to` - _optional_ - End of the interval. Default: now.

* `surround` - _optional_ - If true, return also one value before from and one value after to

### Get an Attribute value

> Get the *Attribute* value and the last time when it changed.

*Tags:* `Functionality`

#### Input Parameters
* `functionalityId` - _required_ - Unique identifier of a *Functionality*.
* `attributeName` - _required_ - Identifier of an *Attribute* inside a *Functionality*.

### Modify an Attribute value

> Modify the value of the *Attribute*.

*Tags:* `Functionality`

#### Input Parameters
* `functionalityId` - _required_ - Unique identifier of a *Functionality*.
* `attributeName` - _required_ - Identifier of an *Attribute* inside a *Functionality*.

### List metadata

> Get the metadata.

*Tags:* `Functionality`

#### Input Parameters
* `functionalityId` - _required_ - Unique identifier of a *Functionality*.

### Modify metadata

> Modify the metadata.<br/>
> Keys are limited to the same format as tags (up to 21 characters, [a-z0-9], starting with [a-z]). Values can be any JSON value.

*Tags:* `Functionality`

#### Input Parameters
* `functionalityId` - _required_ - Unique identifier of a *Functionality*.

### Run an action

> Run an action on the Functionality.

*Tags:* `Action`

#### Input Parameters
* `functionalityId` - _required_ - Unique identifier of a *Functionality*.
* `action` - _required_ - Identifier of an *Action* inside a *Functionality*.

### List tags

> Get the tags of a *Functionality*.

*Tags:* `Functionality`

#### Input Parameters
* `functionalityId` - _required_ - Unique identifier of a *Functionality*.

### Modify tags

> Modify the tags of a *Functionality*.

*Tags:* `Functionality`

#### Input Parameters
* `functionalityId` - _required_ - Unique identifier of a *Functionality*.

### Information about the User

> Get information on the authenticated *User* who does the request.<br/>
> <br/>
> The *login* property is returned only if the *User* is the administrator of<br/>
> the *Account*.

*Tags:* `Entry points`

### Update User information

> Update *User* information (locale).

*Tags:* `Entry points`

### Delete a Notification

> Delete a *Notification*.

*Tags:* `Notification`

#### Input Parameters
* `notificationId` - _required_ - Unique identifier of a *Notification*.

### Information about a Notification

> Get information about a *Notification*.

*Tags:* `Notification`

#### Input Parameters
* `notificationId` - _required_ - Unique identifier of a *Notification*.

### Modify a Notification

> Modify a *Notification*.

*Tags:* `Notification`

#### Input Parameters
* `notificationId` - _required_ - Unique identifier of a *Notification*.

### List metadata

> Get the metadata of the *Notification*.

*Tags:* `Notification`

#### Input Parameters
* `notificationId` - _required_ - Unique identifier of a *Notification*.

### Modify metadata of a Notification

> Modify the metadata of a *Notification*.<br/>
> Keys are limited to the same format as tags (up to 21 characters, [a-z0-9], starting with [a-z]). Values can be any JSON value.

*Tags:* `Notification`

#### Input Parameters
* `notificationId` - _required_ - Unique identifier of a *Notification*.

### List accessible Places

> List the *Places* to which the *Token* has access.

*Tags:* `Entry points`

#### Input Parameters
* `embed-metadata` - _optional_ - Request to include the given keys of metadata in the response. If a key doesn't exist on the resource it is ignored.
**Note:** This only applies to the top level resources.


### Information about a Place

> Get information about a *Place*.

*Tags:* `Place`

#### Input Parameters
* `placeId` - _required_ - Unique identifier of a *Place*.

### Update a Place

> Change information about a *Place*.<br/>
> <br/>
> **Note**: requires full access to the *Account*.

*Tags:* `Place`

#### Input Parameters
* `placeId` - _required_ - Unique identifier of a *Place*.

### List Buses

> Get the list of *Buses* available on the gateway of this *Place*.<br/>
> If `withPairing` is `true`, return only buses that allow device pairing (see `/places/{placeId}/buses/{busId}/pairing`).

*Tags:* `Place`

#### Input Parameters
* `withPairing` - _optional_ - Filter out buses that have no pairing window

### State of the pairing window

> Get the state of the pairing window of the *Bus*.<br/>
> <br/>
> **Note**: requires full access to the *Account*.

*Tags:* `Place`

#### Input Parameters
* `placeId` - _required_ - Unique identifier of a *Place*.
* `busId` - _required_ - Unique identifier of a *Bus*.

### Open/Close the pairing window

> Open/Close the pairing window.<br/>
> <br/>
> **Note**: requires full access to the *Account*.

*Tags:* `Place`

#### Input Parameters
* `placeId` - _required_ - Unique identifier of a *Place*.
* `busId` - _required_ - Unique identifier of a *Bus*.

### List of Devices

> Get the list of *Devices* available in this *Place*.

*Tags:* `Device`

#### Input Parameters
* `devices` - _optional_ - Devices selector. Device tags or device classes or device ids or '*' for any. Multiple values are separated by '|' and interpreted as << OR >>.
* `embed-metadata` - _optional_ - Request to include the given keys of metadata in the response. If a key doesn't exist on the resource it is ignored.
**Note:** This only applies to the top level resources.


### Get autonomy rate of the place

> Compute the autonomy rate of the *Place* on a time period.<br/>
> <br/>
> `autonomy = 1 - (elec_drawn / elec_total_usage)`

*Tags:* `Electricity`

#### Input Parameters
* `when` - _required_ - A time part of the time span.
* `span` - _required_ - Timespan: H (hour), D (day), Wmo (week starting on Monday), Wsu (week starting on Sunday), M (month), Y (year)
    Possible values: H, D, Wmo, Wsu, M, Y.

### Get electricity virtual flows

> Get the mapping of virtual electricity flows to functionalities.<br/>
> <br/>
> Some rules are applied to expand the virtual flows using the concrete<br/>
> flows available.<br/>
> <br/>
> The `factor` tells how each energy value coming from a functionality<br/>
> must be added with values from other functionality to compute the<br/>
> energy of the virtual flow. Factors are usually `1` or `-1`.<br/>
> <br/>
> The `code` property gives the result which may be partial:<br/>
> - If all flows are available, `200000` is returned.<br/>
> - If no flows are available (indicating that the place has no<br/>
>   electricity functionality or that no functionality has been attached<br/>
>   to a flow), the `code` is `200001`. The `missing` property contains<br/>
>   all the requested flows.<br/>
> - If some flows are missing, the `code` is `200002` and the `missing`<br/>
>   property lists them.

*Tags:* `Electricity`

#### Input Parameters
* `flows` - _required_ - Names of the flows requested

### Get electricity flows setup

> Get the mapping of functionalities to electricity flows.<br/>
> <br/>
> A functionality is attached to *at most* one flow.

*Tags:* `Electricity`

#### Input Parameters
* `placeId` - _required_ - Unique identifier of a *Place*.

### Get self-consumption rate of the place

> Compute the self-consumption rate of the *Place* on a time period.<br/>
> <br/>
> `selfConsumption = 1 - (elec_feed_in / elec_total_usage)`

*Tags:* `Electricity`

#### Input Parameters
* `when` - _required_ - A time part of the time span.
* `span` - _required_ - Timespan: H (hour), D (day), Wmo (week starting on Monday), Wsu (week starting on Sunday), M (month), Y (year)
    Possible values: H, D, Wmo, Wsu, M, Y.

### List Functionalities

> Get the list of *Functionalities* available in this *Place*.

*Tags:* `Functionality`

#### Input Parameters
* `embed-metadata` - _optional_ - Request to include the given keys of metadata in the response. If a key doesn't exist on the resource it is ignored.
**Note:** This only applies to the top level resources.

* `devices` - _optional_ - Devices selector. Device tags or device classes or device ids or '*' for any. Multiple values are separated by '|' and interpreted as << OR >>.
* `functionalities` - _optional_ - Functionality selector: Functionality tags or functionality class (optionally, '@' followed by a endpoint in decimal) or '*' for all. Multiple values are separated by '|' and are interpreted as << OR >>.


### List metadata

> Get the metadata.

*Tags:* `Place`

#### Input Parameters
* `placeId` - _required_ - Unique identifier of a *Place*.

### Modify metadata

> Modify the metadata.<br/>
> Keys are limited to the same format as tags (up to 21 characters, [a-z0-9], starting with [a-z]). Values can be any JSON value.

*Tags:* `Place`

#### Input Parameters
* `placeId` - _required_ - Unique identifier of a *Place*.

### List Notifications

> Get the list of *Notifications* available in this *Place*.

*Tags:* `Notification`

#### Input Parameters
* `embed-metadata` - _optional_ - Request to include the given keys of metadata in the response. If a key doesn't exist on the resource it is ignored.
**Note:** This only applies to the top level resources.


### Create a Notification

> Create a new *Notification*.

*Tags:* `Notification`

#### Input Parameters
* `placeId` - _required_ - Unique identifier of a *Place*.

### List Programs

> Get the list of *Programs* available in this *Place*.

*Tags:* `Program`

#### Input Parameters
* `embed-metadata` - _optional_ - Request to include the given keys of metadata in the response. If a key doesn't exist on the resource it is ignored.
**Note:** This only applies to the top level resources.


### Create a Program

> Create a new *Program*.<br/>
> <br/>
> **Note**: requires full access to the *Account*.

*Tags:* `Program`

#### Input Parameters
* `placeId` - _required_ - Unique identifier of a *Place*.

### Run actions

> Run an *Action* on zero, one or multiple *Functionalities* selected with tags.<br/>
> <br/>
> *Device* and *Functionality* selection are combined with << AND >>.<br/>
> <br/>
> If no functionality is matched by the device/functionality selection, an empty array is returned.

*Tags:* `Action`

#### Input Parameters
* `placeId` - _required_ - Unique identifier of a *Place*.
* `action` - _required_ - Identifier of an *Action* inside a *Functionality*.
* `devices` - _required_ - Devices selector. Device tags or device classes or device ids or '*' for any. Multiple values are separated by '|' and interpreted as << OR >>.
* `functionalities` - _required_ - Functionality selector: Functionality tags or functionality class (optionally, '@' followed by a endpoint in decimal) or '*' for all. Multiple values are separated by '|' and are interpreted as << OR >>.


### Delete a Program

> Delete a *Program*.<br/>
> <br/>
> **Note**: requires full access to the *Account*.

*Tags:* `Program`

#### Input Parameters
* `programId` - _required_ - Unique identifier of a *Program*.

### Information about a Program

> Get information about a *Program*.

*Tags:* `Program`

#### Input Parameters
* `programId` - _required_ - Unique identifier of a *Program*.

### Modify a Program

> Modify a *Program*:<br/>
> - name<br/>
> - status (enabled/disabled)<br/>
> - code<br/>
> <br/>
> **Note**: requires full access to the *Account*.

*Tags:* `Program`

#### Input Parameters
* `programId` - _required_ - Unique identifier of a *Program*.

### History of executions of a Program

> Get the execution history list of this *Program*.

*Tags:* `Program`

#### Input Parameters
* `from` - _required_ - Beginning of the time interval.
* `to` - _optional_ - End of the interval. Default: now.


### List metadata

> Get the metadata of the *Program*.

*Tags:* `Program`

#### Input Parameters
* `programId` - _required_ - Unique identifier of a *Program*.

### Modify metadata of a Program

> Modify the metadata of a *Program*.<br/>
> Keys are limited to the same format as tags (up to 21 characters, [a-z0-9], starting with [a-z]). Values can be any JSON value.

*Tags:* `Program`

#### Input Parameters
* `programId` - _required_ - Unique identifier of a *Program*.

### Run the Program

> Launch the *Program*.<br/>
> The result will be available later in the run history.

*Tags:* `Program`

#### Input Parameters
* `programId` - _required_ - Unique identifier of a *Program*.

## License

**flow**ground :- Telekom iPaaS / ijenko-net-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
