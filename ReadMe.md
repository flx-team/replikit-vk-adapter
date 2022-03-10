[![Dot NET 6.0](https://img.shields.io/static/v1?label=DOTNET&message=6.0&color=%23512bd4&style=for-the-badge)](https://dotnet.microsoft.com)
[![Replikit](https://img.shields.io/static/v1?label=Replikit&message=0.3.2&color=%23512bd4&style=for-the-badge)](https://github.com/Replikit/Replikit.git)
[![VK Net](https://img.shields.io/static/v1?label=VKNet&message=1.68.0&color=%23512bd4&style=for-the-badge)](https://github.com/vknet/vk.git)
[![MIT License](https://img.shields.io/static/v1?label=&message=MIT&color=%23512bd4&style=for-the-badge)](License.md)
[![Nullable](https://img.shields.io/static/v1?label=&message=Nullable&color=%23512bd4&style=for-the-badge)](https://www.dotnetcurry.com/csharp/nullable-reference-types-csharp)

<a href="https://www.nuget.org/packages/Replikit.Adapters.FlxTeam.VKontakte">
  <img src="Assets/PackageIcon128.png" alt="NuGet" width="70" />
</a>
  
# VKontakte Adapter

Unofficial VKontakte adapter developed by the Flx Team for the Replikit bot framework.

## Getting Started

In order, to use the VKontakter adapter we must install and configure it.
You can also add several adapters in order to, for example, connect several vk bots.

## Install

Install it.

```bash
dotnet add package Replikit.Adapters.FlxTeam.VKontakte
```

## Add From Group Api

Add it from group api.

```csharp
public override void ConfigureAdapters(IAdapterLoaderOptions options)
{
    // Here you can register adapters
    options.AddVKontakteFromGroup("" /* Vk api token. */, 0 /* Group id. */);
}
```

## Add From User Api

Add it from user api.

```csharp
public override void ConfigureAdapters(IAdapterLoaderOptions options)
{
    // Here you can register adapters
    options.AddVKontakteFromUser("" /* Vk api token. */, 0 /* User id. */);
}
```

## Add From Configurations

Add it from configurations.

```csharp
public override void ConfigureAdapters(IAdapterLoaderOptions options)
{
    // Here you can register adapters
    options.AddVKontakteFromConfigs();
}
```

```jsonc
{
  "replikit": {
    "adapters": [
      {
        "type": "vk",
        "token": "<TOKEN>", // String. Vk api token.
        "identifier": "<IDENTIFIER>", // Ulong. User or group id (read api type).
        "api": "<API_NAME>" // String. Not strict parameter. Api type ("user" or "group"). Default is "group".
      }
    ]
  }
}
```

## Add Multiply

Add it multiply.

```csharp
public override void ConfigureAdapters(IAdapterLoaderOptions options)
{
    // Here you can register adapters
    
    // Add all from configurations.
    options.AddVKontakteFromConfigs();
    
    // For example add one more bot from user api.
    options.AddVKontakteFromUser("" /* Vk api token. */, 0 /* User id. */);
    
    // After started bots from configuration and started bot from user api.
}
```

[Read more about adapters.](https://github.com/Replikit/Replikit/blob/master/docs/getting-started.md)

## Feature Set

Project in early dev.

This table shows the current status of support for different adapter features.
Please note that some of them may not be implemented at the moment, and some may not
be available on a certain platform at all.

Legend:

- **\+** Fully supported
- **~** Partially supported
- **–** Completely unsupported due to platform limitations
- **?** Currently not implemented or investigated

| Feature \ Api          | User | Group |
|------------------------|------|-------|
| **MessageService**     |      |       |
| `Send`                 | +    | +     |
| `Edit`                 | ?    | ?     |
| `Delete`               | ?    | ?     |
| `DeleteMany`           | ?    | ?     |
| `Get`                  | ?    | ?     |
| `GetMany`              | ?    | ?     |
| `Find`                 | ?    | ?     |
| `Pin`                  | ?    | ?     |
| `Unpin`                | ?    | ?     |
| **MemberService**      |      |       |
| `GetMany`              | ?    | ~     |
| `ListMany`             | ?    | ~     |
| `Add`                  | ?    | ?     |
| `Remove`               | ?    | ?     |
| `Ban`                  | ?    | ?     |
| `Unban`                | ?    | ?     |
| **Repository**         |      |       |
| `GetAccountInfo`       | +    | +     |
| `GetChannelInfo`       | +    | +     |
| `ResolveAttachmentUrl` | ?    | ?     |
| **TextTokenizer**      | ~    | ~     |
| **TextFormatter**      | ~    | ~     |
| **EventSource**        | +    | +     |

## Technologies Used

- **[VKNet](https://github.com/vknet/vk.git)** is VKontakte API for NET.
- **[Replikit](https://github.com/Replikit/Replikit.git)** is modern modular platform for building chat bots and virtual assistants
by following the software development best practices and conventions.
A powerful set of abstractions that allows you to create applications 
independent of specific messengers and social networks.

## License

Licensed under the [MIT License](License.md). Copyright 2022 Flx Team.
