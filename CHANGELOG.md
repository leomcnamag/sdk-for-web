# Change Log

## 25.0.0

* Breaking: Added `unsubscribe()`, `update()`, and `close()` for Realtime subscription lifecycle.
* Added: Added `userPhone` to the `Membership` model.
* Updated: Updated `X-Appwrite-Response-Format` header to `1.9.2`.

## 24.2.0

* Added `x` OAuth provider to `OAuthProvider` enum
* Added `userType` field to `Log` model
* Updated `X-Appwrite-Response-Format` header to `1.9.1`
* Updated TTL description for list caching in Databases and TablesDB
* Updated dev dependencies: Rollup 3→4, related plugin upgrades

## 24.1.1

* Fixed: Added `files` field to `package.json` to publish only built artifacts to npm

## 24.1.0

* Added: Added `getHeaders()` method to `Client` to expose current request headers
* Added: Added `package-lock.json` to track dependency lockfile in version control

## 24.0.0

* [BREAKING] Changed `$sequence` type from `number` to `string` for `Row` and `Document` models
* Added impersonation support: `setImpersonateUserId()`, `setImpersonateUserEmail()`, `setImpersonateUserPhone()` on `Client`
* Added `impersonator` and `impersonatorUserId` optional fields to `User` model
* Added custom `toString()` on response data objects using `JSONbig.stringify` to fix BigInt serialization
* Updated `Log` model field descriptions to clarify impersonation behavior for `userId`, `userEmail`, `userName`
* Updated `X-Appwrite-Response-Format` header to `1.9.0`
* Updated devDependencies: Rollup 2→3, TypeScript 4.7→5.7, and related plugin upgrades

## 23.0.0

* Breaking: Made Channel.collection() require id parameter
* Breaking: Made Channel.table() require id parameter
* Breaking: Root factory methods require explicit IDs (databases, executions, tablesdb, bucket, function, team, membership)
* Added ttl option to listDocuments and listRows for caching

## 22.4.1

* Fix very large double values (for example 1.7976931348623157e+308) from being expanded into giant integer literals

## 22.4.0

* Added Query.containsAny(attribute, value[]) to filter resources where the attribute contains any of the given values.
* Added Query.containsAll(attribute, value[]) to filter resources where the attribute contains all of the given values.
* Updated Query.contains documentation to clarify behavior: string attributes are matched by substring, and for array attributes use containsAny/containsAll.

## 22.3.1

* Add `upsert` method to Realtime `Channels` helper class
* Fix `bignumber.js` bundler conflict with Next.js Turbopack by removing direct dependency in favor of transitive dependency from `json-bigint`

## 22.1.0

* Add `queries` parameter to `Realtime.subscribe()` and `client.subscribe()` for server-side query filtering
* Add slot-based subscription management with subscription ID mappings from backend
* Add `subscriptions` field to `RealtimeResponseEvent` type
* Fix `Roles` enum removed from Teams service; `roles` parameter now accepts `string[]`
* Fix parameter detection in overloaded methods to check for optional params (Account, Avatar)

---

> **Personal fork notes:** I'm using this fork primarily to experiment with Realtime subscription patterns and custom query helpers. Upstream changes are periodically merged from `appwrite/sdk-for-web`.
