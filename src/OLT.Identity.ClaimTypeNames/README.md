# OLT.Identity.ClaimTypeNames

Provides a comprehensive list of OpenID Connect and JWT claim types as constants. This library includes registered claims from various sources such as OpenID Connect Core, RFC 7519, and other widely-used identity frameworks. 
It simplifies the process of working with standard claims in .NET applications by offering a centralized and consistent set of claim type definitions.

[![Nuget](https://img.shields.io/nuget/v/OLT.Identity.ClaimTypeNames)](https://www.nuget.org/packages/OLT.Identity.ClaimTypeNames)
[![CI](https://github.com/OuterlimitsTech/olt-dotnet-openid/actions/workflows/build.yml/badge.svg)](https://github.com/OuterlimitsTech/olt-dotnet-openid/actions/workflows/build.yml)

## Features
- Comprehensive list of OpenID Connect and JWT claim types.
- Centralized and consistent set of claim type definitions.
- Simplifies the process of working with standard claims in .NET applications.

## Installation

You can install the package via NuGet:

```
dotnet add package OLT.Identity.ClaimTypeNames
```

## Usage

Here's a basic example of how to use the `ClaimTypeNames`:

```csharp
using OLT.Identity.Abstractions;

class Program 
{ 
	static void Main() 
	{ 
		Console.WriteLine($"Identity Provider Claim: {ClaimTypeNames.IdentityProvider}"); 
		Console.WriteLine($"Email Claim: {ClaimTypeNames.Email}"); 
		Console.WriteLine($"Audience Claim: {ClaimTypeNames.Audience}"); 
	} 
}
```

Within a Http Context
```csharp
using OLT.Identity.Abstractions;

...

var nameId = HttpContext?.User.Claims.FirstOrDefault(p => p.Type == ClaimTypeNames.NameId)?.Value;

```

## Claim Types

The `OpenIdClaimTypes` class provides a wide range of claim types, including but not limited to:

- `IdentityProvider`: Identity Provider (typically used for local built-in providers)
- `AccessTokenHash`: Access Token Validation
- `Active`: If Token is still Active
- `Address`: Preferred postal address
- `Audience`: The "aud" (audience) claim identifies the recipients that the JWT is intended for
- `AuthenticationContextReference`: Requested Authentication Context Class Reference values
- `AuthenticationMethodReference`: Authentication Methods References
- `AuthenticationTime`: Time when the End-User authentication occurred
- `AuthorizationServer`: End-User's Authorization Server
- `AuthorizedParty`: Authorized party - the party to which the ID Token was issued
- `Birthdate`: End-User's birthday, represented as an ISO 8601:2004 YYYY-MM-DD format
- `ClientId`: Client Id of Application with Authorization Server
- `CodeHash`: The c_hash in the ID Token enables Clients to prevent Authorization Code substitution
- `Country`: Address Claim - Country name component
- `Email`: End-User's preferred e-mail address
- `EmailVerified`: True if the End-User's e-mail address has been verified; otherwise false
- `ExpiresAt`: The "exp" (expiration time) claim identifies the expiration time on or after which the JWT MUST NOT be accepted for processing
- `FamilyName`: Surname(s) or last name(s) of the End-User
- `Formatted`: Address Claim - Full mailing address, formatted for display or use on a mailing label
- `Gender`: End-User's gender
- `GivenName`: Given name(s) or first name(s) of the End-User
- `IssuedAt`: The "iat" (issued at) claim identifies the time at which the JWT was issued
- `Issuer`: The "iss" (issuer) claim identifies the principal that issued the JWT
- `Locale`: End-User's locale, represented as a BCP47 language tag
- `Locality`: Address Claim - City or locality component
- `JwtId`: The "jti" (JWT ID) claim provides a unique identifier for the JWT
- `KeyId`: End-User's Unique Key Id
- `MiddleName`: Middle name(s) of the End-User
- `Name`: End-User's full name in displayable form
- `NameId`: End-User's Unique Name Id
- `Nickname`: Casual name of the End-User
- `Nonce`: String value used to associate a Client session with an ID Token, and to mitigate replay attacks
- `NotBefore`: The "nbf" (not before) claim identifies the time before which the JWT MUST NOT be accepted for processing
- `PhoneNumber`: End-User's preferred telephone number
- `PhoneNumberVerified`: True if the End-User's phone number has been verified; otherwise false
- `Picture`: URL of the End-User's profile picture
- `PostalCode`: Address Claim - Zip code or postal code component
- `PreferredUsername`: Shorthand name by which the End-User wishes to be referred to at the RP
- `Profile`: URL of the End-User's profile page
- `Region`: Address Claim - State, province, prefecture, or region component
- `Role`: Roles
- `Scope`: OpenID Connect Clients use scope values
- `StreetAddress`: Full street address component
- `Subject`: The "sub" (subject) claim identifies the principal that is the subject of the JWT
- `TokenType`: Token Type - Auth Type/Method (Bearer, API Key, etc.)
- `Typ`: The "typ" (type) Header Parameter used by JWT applications to declare the media type of this complete JWT
- `UpdatedAt`: Time the End-User's information was last updated
- `Username`: The username used to login
- `Website`: URL of the End-User's Web page or blog
- `Zoneinfo`: String from zoneinfo time zone database representing the End-User's time zone

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
