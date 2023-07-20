---
title: "Event Types"
weight: 10
date: 2023-07-20T13:56:15.503Z
showtoc: true
generated: true
---
<!-- This file was generated from the Vendure source. Do not modify. Instead, re-run the "docs:build" script -->
import MemberInfo from '@site/src/components/MemberInfo';
import GenerationInfo from '@site/src/components/GenerationInfo';
import MemberDescription from '@site/src/components/MemberDescription';


## AccountRegistrationEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/account-registration-event.ts" sourceLine="13" packageName="@vendure/core" />

This event is fired when a new user registers an account, either as a stand-alone signup or after
placing an order.

```ts title="Signature"
class AccountRegistrationEvent extends VendureEvent {
  constructor(ctx: RequestContext, user: User)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, user: <a href='/typescript-api/entities/user#user'>User</a>) => AccountRegistrationEvent"   />




## AccountVerifiedEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/account-verified-event.ts" sourceLine="13" packageName="@vendure/core" />

This event is fired when a users email address successfully gets verified after
the `verifyCustomerAccount` mutation was executed.

```ts title="Signature"
class AccountVerifiedEvent extends VendureEvent {
  constructor(ctx: RequestContext, customer: Customer)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, customer: <a href='/typescript-api/entities/customer#customer'>Customer</a>) => AccountVerifiedEvent"   />




## AdministratorEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/administrator-event.ts" sourceLine="18" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/administrator#administrator'>Administrator</a> is added, updated or deleted.

```ts title="Signature"
class AdministratorEvent extends VendureEntityEvent<Administrator, AdministratorInputTypes> {
  constructor(ctx: RequestContext, entity: Administrator, type: 'created' | 'updated' | 'deleted', input?: AdministratorInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/administrator#administrator'>Administrator</a>, AdministratorInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/administrator#administrator'>Administrator</a>, type: 'created' | 'updated' | 'deleted', input?: AdministratorInputTypes) => AdministratorEvent"   />




## AssetChannelEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/asset-channel-event.ts" sourceLine="15" packageName="@vendure/core" />

This event is fired whenever an <a href='/typescript-api/entities/asset#asset'>Asset</a> is assigned or removed
From a channel.

```ts title="Signature"
class AssetChannelEvent extends VendureEvent {
  constructor(ctx: RequestContext, asset: Asset, channelId: ID, type: 'assigned' | 'removed')
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, asset: <a href='/typescript-api/entities/asset#asset'>Asset</a>, channelId: <a href='/typescript-api/common/id#id'>ID</a>, type: 'assigned' | 'removed') => AssetChannelEvent"   />




## AssetEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/asset-event.ts" sourceLine="18" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/asset#asset'>Asset</a> is added, updated or deleted.

```ts title="Signature"
class AssetEvent extends VendureEntityEvent<Asset, AssetInputTypes> {
  constructor(ctx: RequestContext, entity: Asset, type: 'created' | 'updated' | 'deleted', input?: AssetInputTypes)
  asset: Asset
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/asset#asset'>Asset</a>, AssetInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/asset#asset'>Asset</a>, type: 'created' | 'updated' | 'deleted', input?: AssetInputTypes) => AssetEvent"   />


### asset

<MemberInfo kind="property" type="<a href='/typescript-api/entities/asset#asset'>Asset</a>"  since="1.4"  />




## AttemptedLoginEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/attempted-login-event.ts" sourceLine="14" packageName="@vendure/core" />

This event is fired when an attempt is made to log in via the shop or admin API `login` mutation.
The `strategy` represents the name of the AuthenticationStrategy used in the login attempt.
If the "native" strategy is used, the additional `identifier` property will be available.

```ts title="Signature"
class AttemptedLoginEvent extends VendureEvent {
  constructor(ctx: RequestContext, strategy: string, identifier?: string)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, strategy: string, identifier?: string) => AttemptedLoginEvent"   />




## ChangeChannelEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/change-channel-event.ts" sourceLine="17" packageName="@vendure/core" since="1.4" />

This event is fired whenever an <a href='/typescript-api/entities/interfaces#channelaware'>ChannelAware</a> entity is assigned or removed
from a channel. The entity property contains the value before updating the channels.

```ts title="Signature"
class ChangeChannelEvent<T extends ChannelAware & VendureEntity> extends VendureEvent {
  constructor(ctx: RequestContext, entity: T, channelIds: ID[], type: 'assigned' | 'removed', entityType?: Type<T>)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: T, channelIds: <a href='/typescript-api/common/id#id'>ID</a>[], type: 'assigned' | 'removed', entityType?: Type&#60;T&#62;) => ChangeChannelEvent"   />




## ChannelEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/channel-event.ts" sourceLine="18" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/channel#channel'>Channel</a> is added, updated or deleted.

```ts title="Signature"
class ChannelEvent extends VendureEntityEvent<Channel, ChannelInputTypes> {
  constructor(ctx: RequestContext, entity: Channel, type: 'created' | 'updated' | 'deleted', input?: ChannelInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/channel#channel'>Channel</a>, ChannelInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/channel#channel'>Channel</a>, type: 'created' | 'updated' | 'deleted', input?: ChannelInputTypes) => ChannelEvent"   />




## CollectionEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/collection-event.ts" sourceLine="18" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/collection#collection'>Collection</a> is added, updated or deleted.

```ts title="Signature"
class CollectionEvent extends VendureEntityEvent<Collection, CollectionInputTypes> {
  constructor(ctx: RequestContext, entity: Collection, type: 'created' | 'updated' | 'deleted', input?: CollectionInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/collection#collection'>Collection</a>, CollectionInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/collection#collection'>Collection</a>, type: 'created' | 'updated' | 'deleted', input?: CollectionInputTypes) => CollectionEvent"   />




## CollectionModificationEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/collection-modification-event.ts" sourceLine="18" packageName="@vendure/core" />

This event is fired whenever a Collection is modified in some way. The `productVariantIds`
argument is an array of ids of all ProductVariants which:

1. were part of this collection prior to modification and are no longer
2. are now part of this collection after modification but were not before

```ts title="Signature"
class CollectionModificationEvent extends VendureEvent {
  constructor(ctx: RequestContext, collection: Collection, productVariantIds: ID[])
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, collection: <a href='/typescript-api/entities/collection#collection'>Collection</a>, productVariantIds: <a href='/typescript-api/common/id#id'>ID</a>[]) => CollectionModificationEvent"   />




## CountryEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/country-event.ts" sourceLine="18" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/country#country'>Country</a> is added, updated or deleted.

```ts title="Signature"
class CountryEvent extends VendureEntityEvent<Country, CountryInputTypes> {
  constructor(ctx: RequestContext, entity: Country, type: 'created' | 'updated' | 'deleted', input?: CountryInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/country#country'>Country</a>, CountryInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/country#country'>Country</a>, type: 'created' | 'updated' | 'deleted', input?: CountryInputTypes) => CountryEvent"   />




## CouponCodeEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/coupon-code-event.ts" sourceLine="15" packageName="@vendure/core" since="1.4" />

This event is fired whenever an coupon code of an active <a href='/typescript-api/entities/promotion#promotion'>Promotion</a>
is assigned or removed to an <a href='/typescript-api/entities/order#order'>Order</a>.

```ts title="Signature"
class CouponCodeEvent extends VendureEvent {
  constructor(ctx: RequestContext, couponCode: string, orderId: ID, type: 'assigned' | 'removed')
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, couponCode: string, orderId: <a href='/typescript-api/common/id#id'>ID</a>, type: 'assigned' | 'removed') => CouponCodeEvent"   />




## CustomerAddressEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/customer-address-event.ts" sourceLine="22" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/address#address'>Address</a> is added, updated
or deleted.

```ts title="Signature"
class CustomerAddressEvent extends VendureEntityEvent<Address, CustomerAddressInputTypes> {
  constructor(ctx: RequestContext, entity: Address, type: 'created' | 'updated' | 'deleted', input?: CustomerAddressInputTypes)
  address: Address
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/address#address'>Address</a>, CustomerAddressInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/address#address'>Address</a>, type: 'created' | 'updated' | 'deleted', input?: CustomerAddressInputTypes) => CustomerAddressEvent"   />


### address

<MemberInfo kind="property" type="<a href='/typescript-api/entities/address#address'>Address</a>"   />




## CustomerEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/customer-event.ts" sourceLine="22" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/customer#customer'>Customer</a> is added, updated
or deleted.

```ts title="Signature"
class CustomerEvent extends VendureEntityEvent<Customer, CustomerInputTypes> {
  constructor(ctx: RequestContext, entity: Customer, type: 'created' | 'updated' | 'deleted', input?: CustomerInputTypes)
  customer: Customer
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/customer#customer'>Customer</a>, CustomerInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/customer#customer'>Customer</a>, type: 'created' | 'updated' | 'deleted', input?: CustomerInputTypes) => CustomerEvent"   />


### customer

<MemberInfo kind="property" type="<a href='/typescript-api/entities/customer#customer'>Customer</a>"  since="1.4"  />




## CustomerGroupChangeEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/customer-group-change-event.ts" sourceLine="15" packageName="@vendure/core" since="1.4" />

This event is fired whenever one or more <a href='/typescript-api/entities/customer#customer'>Customer</a> is assigned to or removed from a
<a href='/typescript-api/entities/customer-group#customergroup'>CustomerGroup</a>.

```ts title="Signature"
class CustomerGroupChangeEvent extends VendureEvent {
  constructor(ctx: RequestContext, customers: Customer[], customGroup: CustomerGroup, type: 'assigned' | 'removed')
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, customers: <a href='/typescript-api/entities/customer#customer'>Customer</a>[], customGroup: <a href='/typescript-api/entities/customer-group#customergroup'>CustomerGroup</a>, type: 'assigned' | 'removed') => CustomerGroupChangeEvent"   />




## CustomerGroupEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/customer-group-event.ts" sourceLine="18" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/customer-group#customergroup'>CustomerGroup</a> is added, updated or deleted.

```ts title="Signature"
class CustomerGroupEvent extends VendureEntityEvent<CustomerGroup, CustomerGroupInputTypes> {
  constructor(ctx: RequestContext, entity: CustomerGroup, type: 'created' | 'updated' | 'deleted', input?: CustomerGroupInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/customer-group#customergroup'>CustomerGroup</a>, CustomerGroupInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/customer-group#customergroup'>CustomerGroup</a>, type: 'created' | 'updated' | 'deleted', input?: CustomerGroupInputTypes) => CustomerGroupEvent"   />




## FacetEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/facet-event.ts" sourceLine="18" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/facet#facet'>Facet</a> is added, updated or deleted.

```ts title="Signature"
class FacetEvent extends VendureEntityEvent<Facet, FacetInputTypes> {
  constructor(ctx: RequestContext, entity: Facet, type: 'created' | 'updated' | 'deleted', input?: FacetInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/facet#facet'>Facet</a>, FacetInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/facet#facet'>Facet</a>, type: 'created' | 'updated' | 'deleted', input?: FacetInputTypes) => FacetEvent"   />




## FacetValueEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/facet-value-event.ts" sourceLine="26" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/facet-value#facetvalue'>FacetValue</a> is added, updated or deleted.

```ts title="Signature"
class FacetValueEvent extends VendureEntityEvent<FacetValue, FacetValueInputTypes> {
  constructor(ctx: RequestContext, entity: FacetValue, type: 'created' | 'updated' | 'deleted', input?: FacetValueInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/facet-value#facetvalue'>FacetValue</a>, FacetValueInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/facet-value#facetvalue'>FacetValue</a>, type: 'created' | 'updated' | 'deleted', input?: FacetValueInputTypes) => FacetValueEvent"   />




## FulfillmentEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/fulfillment-event.ts" sourceLine="27" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/fulfillment#fulfillment'>Fulfillment</a> is added. The type is always `created`.

```ts title="Signature"
class FulfillmentEvent extends VendureEntityEvent<Fulfillment, CreateFulfillmentInput> {
  constructor(ctx: RequestContext, entity: Fulfillment, input?: CreateFulfillmentInput)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/fulfillment#fulfillment'>Fulfillment</a>, CreateFulfillmentInput&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/fulfillment#fulfillment'>Fulfillment</a>, input?: CreateFulfillmentInput) => FulfillmentEvent"   />




## FulfillmentStateTransitionEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/fulfillment-state-transition-event.ts" sourceLine="13" packageName="@vendure/core" />

This event is fired whenever an <a href='/typescript-api/entities/fulfillment#fulfillment'>Fulfillment</a> transitions from one <a href='/typescript-api/fulfillment/fulfillment-state#fulfillmentstate'>FulfillmentState</a> to another.

```ts title="Signature"
class FulfillmentStateTransitionEvent extends VendureEvent {
  constructor(fromState: FulfillmentState, toState: FulfillmentState, ctx: RequestContext, fulfillment: Fulfillment)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(fromState: <a href='/typescript-api/fulfillment/fulfillment-state#fulfillmentstate'>FulfillmentState</a>, toState: <a href='/typescript-api/fulfillment/fulfillment-state#fulfillmentstate'>FulfillmentState</a>, ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, fulfillment: <a href='/typescript-api/entities/fulfillment#fulfillment'>Fulfillment</a>) => FulfillmentStateTransitionEvent"   />




## GlobalSettingsEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/global-settings-event.ts" sourceLine="16" packageName="@vendure/core" since="1.4" />

This event is fired whenever a {@link GlobalSettings} is added. The type is always `updated`, because it's
only created once and never deleted.

```ts title="Signature"
class GlobalSettingsEvent extends VendureEntityEvent<GlobalSettings, UpdateGlobalSettingsInput> {
  constructor(ctx: RequestContext, entity: GlobalSettings, input?: UpdateGlobalSettingsInput)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;GlobalSettings, UpdateGlobalSettingsInput&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: GlobalSettings, input?: UpdateGlobalSettingsInput) => GlobalSettingsEvent"   />




## HistoryEntryEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/history-entry-event.ts" sourceLine="23" packageName="@vendure/core" since="1.4" />

This event is fired whenever one <a href='/typescript-api/entities/history-entry#historyentry'>HistoryEntry</a> is added, updated or deleted.

```ts title="Signature"
class HistoryEntryEvent extends VendureEntityEvent<HistoryEntry, HistoryInput> {
  public readonly public readonly historyType: 'order' | 'customer' | string;
  constructor(ctx: RequestContext, entity: HistoryEntry, type: 'created' | 'updated' | 'deleted', historyType: 'order' | 'customer' | string, input?: HistoryInput)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/history-entry#historyentry'>HistoryEntry</a>, HistoryInput&#62;



### historyType

<MemberInfo kind="property" type="'order' | 'customer' | string"   />


### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/history-entry#historyentry'>HistoryEntry</a>, type: 'created' | 'updated' | 'deleted', historyType: 'order' | 'customer' | string, input?: HistoryInput) => HistoryEntryEvent"   />




## IdentifierChangeEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/identifier-change-event.ts" sourceLine="13" packageName="@vendure/core" />

This event is fired when a registered user successfully changes the identifier (ie email address)
associated with their account.

```ts title="Signature"
class IdentifierChangeEvent extends VendureEvent {
  constructor(ctx: RequestContext, user: User, oldIdentifier: string)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, user: <a href='/typescript-api/entities/user#user'>User</a>, oldIdentifier: string) => IdentifierChangeEvent"   />




## IdentifierChangeRequestEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/identifier-change-request-event.ts" sourceLine="13" packageName="@vendure/core" />

This event is fired when a registered user requests to update the identifier (ie email address)
associated with the account.

```ts title="Signature"
class IdentifierChangeRequestEvent extends VendureEvent {
  constructor(ctx: RequestContext, user: User)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, user: <a href='/typescript-api/entities/user#user'>User</a>) => IdentifierChangeRequestEvent"   />




## InitializerEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/initializer-event.ts" sourceLine="11" packageName="@vendure/core" since="1.7.0" />

This event is fired when vendure finished initializing its services inside the {@code InitializerService}

```ts title="Signature"
class InitializerEvent extends VendureEvent {
  constructor()
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="() => InitializerEvent"   />




## LoginEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/login-event.ts" sourceLine="12" packageName="@vendure/core" />

This event is fired when a user successfully logs in via the shop or admin API `login` mutation.

```ts title="Signature"
class LoginEvent extends VendureEvent {
  constructor(ctx: RequestContext, user: User)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, user: <a href='/typescript-api/entities/user#user'>User</a>) => LoginEvent"   />




## LogoutEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/logout-event.ts" sourceLine="12" packageName="@vendure/core" />

This event is fired when a user logs out via the shop or admin API `logout` mutation.

```ts title="Signature"
class LogoutEvent extends VendureEvent {
  constructor(ctx: RequestContext)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>) => LogoutEvent"   />




## OrderEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/order-event.ts" sourceLine="13" packageName="@vendure/core" />

This event is fired whenever an <a href='/typescript-api/entities/order#order'>Order</a> is added, updated
or deleted.

```ts title="Signature"
class OrderEvent extends VendureEvent {
  constructor(ctx: RequestContext, order: Order, type: 'created' | 'updated' | 'deleted')
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, order: <a href='/typescript-api/entities/order#order'>Order</a>, type: 'created' | 'updated' | 'deleted') => OrderEvent"   />




## OrderLineEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/order-line-event.ts" sourceLine="13" packageName="@vendure/core" />

This event is fired whenever an <a href='/typescript-api/entities/order-line#orderline'>OrderLine</a> is added, updated
or deleted.

```ts title="Signature"
class OrderLineEvent extends VendureEvent {
  constructor(ctx: RequestContext, order: Order, orderLine: OrderLine, type: 'created' | 'updated' | 'deleted')
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, order: <a href='/typescript-api/entities/order#order'>Order</a>, orderLine: <a href='/typescript-api/entities/order-line#orderline'>OrderLine</a>, type: 'created' | 'updated' | 'deleted') => OrderLineEvent"   />




## OrderPlacedEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/order-placed-event.ts" sourceLine="17" packageName="@vendure/core" />

This event is fired whenever an <a href='/typescript-api/entities/order#order'>Order</a> is set as "placed", which by default is
when it transitions from 'ArrangingPayment' to either 'PaymentAuthorized' or 'PaymentSettled'.

Note that the exact point that it is set as "placed" can be configured according to the
<a href='/typescript-api/orders/order-placed-strategy#orderplacedstrategy'>OrderPlacedStrategy</a>.

```ts title="Signature"
class OrderPlacedEvent extends VendureEvent {
  constructor(fromState: OrderState, toState: OrderState, ctx: RequestContext, order: Order)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(fromState: <a href='/typescript-api/orders/order-process#orderstate'>OrderState</a>, toState: <a href='/typescript-api/orders/order-process#orderstate'>OrderState</a>, ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, order: <a href='/typescript-api/entities/order#order'>Order</a>) => OrderPlacedEvent"   />




## OrderStateTransitionEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/order-state-transition-event.ts" sourceLine="13" packageName="@vendure/core" />

This event is fired whenever an <a href='/typescript-api/entities/order#order'>Order</a> transitions from one <a href='/typescript-api/orders/order-process#orderstate'>OrderState</a> to another.

```ts title="Signature"
class OrderStateTransitionEvent extends VendureEvent {
  constructor(fromState: OrderState, toState: OrderState, ctx: RequestContext, order: Order)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(fromState: <a href='/typescript-api/orders/order-process#orderstate'>OrderState</a>, toState: <a href='/typescript-api/orders/order-process#orderstate'>OrderState</a>, ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, order: <a href='/typescript-api/entities/order#order'>Order</a>) => OrderStateTransitionEvent"   />




## PasswordResetEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/password-reset-event.ts" sourceLine="12" packageName="@vendure/core" />

This event is fired when a Customer requests a password reset email.

```ts title="Signature"
class PasswordResetEvent extends VendureEvent {
  constructor(ctx: RequestContext, user: User)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, user: <a href='/typescript-api/entities/user#user'>User</a>) => PasswordResetEvent"   />




## PasswordResetVerifiedEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/password-reset-verified-event.ts" sourceLine="13" packageName="@vendure/core" since="1.4" />

This event is fired when a password reset is executed with a verified token.

```ts title="Signature"
class PasswordResetVerifiedEvent extends VendureEvent {
  constructor(ctx: RequestContext, user: User)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, user: <a href='/typescript-api/entities/user#user'>User</a>) => PasswordResetVerifiedEvent"   />




## PaymentMethodEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/payment-method-event.ts" sourceLine="18" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/payment-method#paymentmethod'>PaymentMethod</a> is added, updated
or deleted.

```ts title="Signature"
class PaymentMethodEvent extends VendureEntityEvent<PaymentMethod, PaymentMethodInputTypes> {
  constructor(ctx: RequestContext, entity: PaymentMethod, type: 'created' | 'updated' | 'deleted', input?: PaymentMethodInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/payment-method#paymentmethod'>PaymentMethod</a>, PaymentMethodInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/payment-method#paymentmethod'>PaymentMethod</a>, type: 'created' | 'updated' | 'deleted', input?: PaymentMethodInputTypes) => PaymentMethodEvent"   />




## PaymentStateTransitionEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/payment-state-transition-event.ts" sourceLine="15" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/payment#payment'>Payment</a> transitions from one <a href='/typescript-api/payment/payment-state#paymentstate'>PaymentState</a> to another, e.g.
a Payment is authorized by the payment provider.

```ts title="Signature"
class PaymentStateTransitionEvent extends VendureEvent {
  constructor(fromState: PaymentState, toState: PaymentState, ctx: RequestContext, payment: Payment, order: Order)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(fromState: <a href='/typescript-api/payment/payment-state#paymentstate'>PaymentState</a>, toState: <a href='/typescript-api/payment/payment-state#paymentstate'>PaymentState</a>, ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, payment: <a href='/typescript-api/entities/payment#payment'>Payment</a>, order: <a href='/typescript-api/entities/order#order'>Order</a>) => PaymentStateTransitionEvent"   />




## ProductChannelEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/product-channel-event.ts" sourceLine="15" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/product#product'>Product</a> is added, updated
or deleted.

```ts title="Signature"
class ProductChannelEvent extends VendureEvent {
  constructor(ctx: RequestContext, product: Product, channelId: ID, type: 'assigned' | 'removed')
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, product: <a href='/typescript-api/entities/product#product'>Product</a>, channelId: <a href='/typescript-api/common/id#id'>ID</a>, type: 'assigned' | 'removed') => ProductChannelEvent"   />




## ProductEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/product-event.ts" sourceLine="18" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/product#product'>Product</a> is added, updated
or deleted.

```ts title="Signature"
class ProductEvent extends VendureEntityEvent<Product, ProductInputTypes> {
  constructor(ctx: RequestContext, entity: Product, type: 'created' | 'updated' | 'deleted', input?: ProductInputTypes)
  product: Product
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/product#product'>Product</a>, ProductInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/product#product'>Product</a>, type: 'created' | 'updated' | 'deleted', input?: ProductInputTypes) => ProductEvent"   />


### product

<MemberInfo kind="property" type="<a href='/typescript-api/entities/product#product'>Product</a>"  since="1.4"  />




## ProductOptionEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/product-option-event.ts" sourceLine="26" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/product-option#productoption'>ProductOption</a> is added or updated.

```ts title="Signature"
class ProductOptionEvent extends VendureEntityEvent<ProductOption, ProductOptionInputTypes> {
  constructor(ctx: RequestContext, entity: ProductOption, type: 'created' | 'updated' | 'deleted', input?: ProductOptionInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/product-option#productoption'>ProductOption</a>, ProductOptionInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/product-option#productoption'>ProductOption</a>, type: 'created' | 'updated' | 'deleted', input?: ProductOptionInputTypes) => ProductOptionEvent"   />




## ProductOptionGroupChangeEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/product-option-group-change-event.ts" sourceLine="15" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/product-option-group#productoptiongroup'>ProductOptionGroup</a> is assigned or removed from a <a href='/typescript-api/entities/product#product'>Product</a>.

```ts title="Signature"
class ProductOptionGroupChangeEvent extends VendureEvent {
  constructor(ctx: RequestContext, product: Product, optionGroupId: ID, type: 'assigned' | 'removed')
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, product: <a href='/typescript-api/entities/product#product'>Product</a>, optionGroupId: <a href='/typescript-api/common/id#id'>ID</a>, type: 'assigned' | 'removed') => ProductOptionGroupChangeEvent"   />




## ProductOptionGroupEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/product-option-group-event.ts" sourceLine="21" packageName="@vendure/core" since="1.4" />

This event is fired whenever a <a href='/typescript-api/entities/product-option-group#productoptiongroup'>ProductOptionGroup</a> is added or updated.

```ts title="Signature"
class ProductOptionGroupEvent extends VendureEntityEvent<
    ProductOptionGroup,
    ProductOptionGroupInputTypes
> {
  constructor(ctx: RequestContext, entity: ProductOptionGroup, type: 'created' | 'updated' | 'deleted', input?: ProductOptionGroupInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/product-option-group#productoptiongroup'>ProductOptionGroup</a>, type: 'created' | 'updated' | 'deleted', input?: ProductOptionGroupInputTypes) => ProductOptionGroupEvent"   />




## ProductVariantChannelEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/product-variant-channel-event.ts" sourceLine="14" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/product-variant#productvariant'>ProductVariant</a> is assigned or removed from a <a href='/typescript-api/entities/channel#channel'>Channel</a>.

```ts title="Signature"
class ProductVariantChannelEvent extends VendureEvent {
  constructor(ctx: RequestContext, productVariant: ProductVariant, channelId: ID, type: 'assigned' | 'removed')
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, productVariant: <a href='/typescript-api/entities/product-variant#productvariant'>ProductVariant</a>, channelId: <a href='/typescript-api/common/id#id'>ID</a>, type: 'assigned' | 'removed') => ProductVariantChannelEvent"   />




## ProductVariantEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/product-variant-event.ts" sourceLine="18" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/product-variant#productvariant'>ProductVariant</a> is added, updated
or deleted.

```ts title="Signature"
class ProductVariantEvent extends VendureEntityEvent<ProductVariant[], ProductVariantInputTypes> {
  constructor(ctx: RequestContext, entity: ProductVariant[], type: 'created' | 'updated' | 'deleted', input?: ProductVariantInputTypes)
  variants: ProductVariant[]
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/product-variant#productvariant'>ProductVariant</a>[], ProductVariantInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/product-variant#productvariant'>ProductVariant</a>[], type: 'created' | 'updated' | 'deleted', input?: ProductVariantInputTypes) => ProductVariantEvent"   />


### variants

<MemberInfo kind="property" type="<a href='/typescript-api/entities/product-variant#productvariant'>ProductVariant</a>[]"  since="1.4"  />




## PromotionEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/promotion-event.ts" sourceLine="18" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/promotion#promotion'>Promotion</a> is added, updated
or deleted.

```ts title="Signature"
class PromotionEvent extends VendureEntityEvent<Promotion, PromotionInputTypes> {
  constructor(ctx: RequestContext, entity: Promotion, type: 'created' | 'updated' | 'deleted', input?: PromotionInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/promotion#promotion'>Promotion</a>, PromotionInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/promotion#promotion'>Promotion</a>, type: 'created' | 'updated' | 'deleted', input?: PromotionInputTypes) => PromotionEvent"   />




## ProvinceEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/province-event.ts" sourceLine="18" packageName="@vendure/core" since="2.0" />

This event is fired whenever a <a href='/typescript-api/entities/province#province'>Province</a> is added, updated or deleted.

```ts title="Signature"
class ProvinceEvent extends VendureEntityEvent<Province, ProvinceInputTypes> {
  constructor(ctx: RequestContext, entity: Province, type: 'created' | 'updated' | 'deleted', input?: ProvinceInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/province#province'>Province</a>, ProvinceInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/province#province'>Province</a>, type: 'created' | 'updated' | 'deleted', input?: ProvinceInputTypes) => ProvinceEvent"   />




## RefundStateTransitionEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/refund-state-transition-event.ts" sourceLine="14" packageName="@vendure/core" />

This event is fired whenever a {@link Refund} transitions from one <a href='/typescript-api/payment/refund-state#refundstate'>RefundState</a> to another.

```ts title="Signature"
class RefundStateTransitionEvent extends VendureEvent {
  constructor(fromState: RefundState, toState: RefundState, ctx: RequestContext, refund: Refund, order: Order)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(fromState: <a href='/typescript-api/payment/refund-state#refundstate'>RefundState</a>, toState: <a href='/typescript-api/payment/refund-state#refundstate'>RefundState</a>, ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, refund: Refund, order: <a href='/typescript-api/entities/order#order'>Order</a>) => RefundStateTransitionEvent"   />




## RoleChangeEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/role-change-event.ts" sourceLine="16" packageName="@vendure/core" since="1.4" />

This event is fired whenever one <a href='/typescript-api/entities/role#role'>Role</a> is assigned or removed from a user.
The property `roleIds` only contains the removed or assigned role ids.

```ts title="Signature"
class RoleChangeEvent extends VendureEvent {
  constructor(ctx: RequestContext, admin: Administrator, roleIds: ID[], type: 'assigned' | 'removed')
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, admin: <a href='/typescript-api/entities/administrator#administrator'>Administrator</a>, roleIds: <a href='/typescript-api/common/id#id'>ID</a>[], type: 'assigned' | 'removed') => RoleChangeEvent"   />




## RoleEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/role-event.ts" sourceLine="18" packageName="@vendure/core" since="1.4" />

This event is fired whenever one <a href='/typescript-api/entities/role#role'>Role</a> is added, updated or deleted.

```ts title="Signature"
class RoleEvent extends VendureEntityEvent<Role, RoleInputTypes> {
  constructor(ctx: RequestContext, entity: Role, type: 'created' | 'updated' | 'deleted', input?: RoleInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/role#role'>Role</a>, RoleInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/role#role'>Role</a>, type: 'created' | 'updated' | 'deleted', input?: RoleInputTypes) => RoleEvent"   />




## SearchEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/search-event.ts" sourceLine="18" packageName="@vendure/core" since="1.6.0" />

This event is fired whenever a search query is executed.

```ts title="Signature"
class SearchEvent extends VendureEvent {
  constructor(ctx: RequestContext, input: ExtendedSearchInput)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, input: ExtendedSearchInput) => SearchEvent"   />




## SellerEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/seller-event.ts" sourceLine="19" packageName="@vendure/core" since="2.0.1" />

This event is fired whenever one <a href='/typescript-api/entities/seller#seller'>Seller</a> is added, updated or deleted.

```ts title="Signature"
class SellerEvent extends VendureEntityEvent<Seller, SellerInputTypes> {
  constructor(ctx: RequestContext, entity: Seller, type: 'created' | 'updated' | 'deleted', input?: SellerInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/seller#seller'>Seller</a>, SellerInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/seller#seller'>Seller</a>, type: 'created' | 'updated' | 'deleted', input?: SellerInputTypes) => SellerEvent"   />




## ShippingMethodEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/shipping-method-event.ts" sourceLine="18" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/shipping-method#shippingmethod'>ShippingMethod</a> is added, updated
or deleted.

```ts title="Signature"
class ShippingMethodEvent extends VendureEntityEvent<ShippingMethod, ShippingMethodInputTypes> {
  constructor(ctx: RequestContext, entity: ShippingMethod, type: 'created' | 'updated' | 'deleted', input?: ShippingMethodInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/shipping-method#shippingmethod'>ShippingMethod</a>, ShippingMethodInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/shipping-method#shippingmethod'>ShippingMethod</a>, type: 'created' | 'updated' | 'deleted', input?: ShippingMethodInputTypes) => ShippingMethodEvent"   />




## StockMovementEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/stock-movement-event.ts" sourceLine="16" packageName="@vendure/core" since="1.1.0" />

This event is fired whenever a <a href='/typescript-api/entities/stock-movement#stockmovement'>StockMovement</a> entity is created, which occurs when the saleable
stock level of a ProductVariant is altered due to things like sales, manual adjustments, and cancellations.

```ts title="Signature"
class StockMovementEvent extends VendureEvent {
  public readonly public readonly type: StockMovementType;
  constructor(ctx: RequestContext, stockMovements: StockMovement[])
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### type

<MemberInfo kind="property" type="StockMovementType"   />


### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, stockMovements: <a href='/typescript-api/entities/stock-movement#stockmovement'>StockMovement</a>[]) => StockMovementEvent"   />




## TaxCategoryEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/tax-category-event.ts" sourceLine="18" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/tax-category#taxcategory'>TaxCategory</a> is added, updated
or deleted.

```ts title="Signature"
class TaxCategoryEvent extends VendureEntityEvent<TaxCategory, TaxCategoryInputTypes> {
  constructor(ctx: RequestContext, entity: TaxCategory, type: 'created' | 'updated' | 'deleted', input?: TaxCategoryInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/tax-category#taxcategory'>TaxCategory</a>, TaxCategoryInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/tax-category#taxcategory'>TaxCategory</a>, type: 'created' | 'updated' | 'deleted', input?: TaxCategoryInputTypes) => TaxCategoryEvent"   />




## TaxRateEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/tax-rate-event.ts" sourceLine="18" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/tax-rate#taxrate'>TaxRate</a> is added, updated
or deleted.

```ts title="Signature"
class TaxRateEvent extends VendureEntityEvent<TaxRate, TaxRateInputTypes> {
  constructor(ctx: RequestContext, entity: TaxRate, type: 'created' | 'updated' | 'deleted', input?: TaxRateInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/tax-rate#taxrate'>TaxRate</a>, TaxRateInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/tax-rate#taxrate'>TaxRate</a>, type: 'created' | 'updated' | 'deleted', input?: TaxRateInputTypes) => TaxRateEvent"   />




## TaxRateModificationEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/tax-rate-modification-event.ts" sourceLine="13" packageName="@vendure/core" />

This event is fired whenever a TaxRate is changed

```ts title="Signature"
class TaxRateModificationEvent extends VendureEvent {
  constructor(ctx: RequestContext, taxRate: TaxRate)
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, taxRate: <a href='/typescript-api/entities/tax-rate#taxrate'>TaxRate</a>) => TaxRateModificationEvent"   />




## ZoneEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/zone-event.ts" sourceLine="18" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/zone#zone'>Zone</a> is added, updated
or deleted.

```ts title="Signature"
class ZoneEvent extends VendureEntityEvent<Zone, ZoneInputTypes> {
  constructor(ctx: RequestContext, entity: Zone, type: 'created' | 'updated' | 'deleted', input?: ZoneInputTypes)
}
```
Extends

 * <a href='/typescript-api/events/vendure-entity-event#vendureentityevent'>VendureEntityEvent</a>&#60;<a href='/typescript-api/entities/zone#zone'>Zone</a>, ZoneInputTypes&#62;



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/zone#zone'>Zone</a>, type: 'created' | 'updated' | 'deleted', input?: ZoneInputTypes) => ZoneEvent"   />




## ZoneMembersEvent

<GenerationInfo sourceFile="packages/core/src/event-bus/events/zone-members-event.ts" sourceLine="15" packageName="@vendure/core" />

This event is fired whenever a <a href='/typescript-api/entities/zone#zone'>Zone</a> gets <a href='/typescript-api/entities/country#country'>Country</a> members assigned or removed
The `entity` property contains the zone with the already updated member field.

```ts title="Signature"
class ZoneMembersEvent extends VendureEvent {
  constructor(ctx: RequestContext, entity: Zone, type: 'assigned' | 'removed', memberIds: ID[])
}
```
Extends

 * <a href='/typescript-api/events/vendure-event#vendureevent'>VendureEvent</a>



### constructor

<MemberInfo kind="method" type="(ctx: <a href='/typescript-api/request/request-context#requestcontext'>RequestContext</a>, entity: <a href='/typescript-api/entities/zone#zone'>Zone</a>, type: 'assigned' | 'removed', memberIds: <a href='/typescript-api/common/id#id'>ID</a>[]) => ZoneMembersEvent"   />

