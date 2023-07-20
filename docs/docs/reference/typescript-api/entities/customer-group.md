---
title: "CustomerGroup"
weight: 10
date: 2023-07-20T13:56:15.131Z
showtoc: true
generated: true
---
<!-- This file was generated from the Vendure source. Do not modify. Instead, re-run the "docs:build" script -->
import MemberInfo from '@site/src/components/MemberInfo';
import GenerationInfo from '@site/src/components/GenerationInfo';
import MemberDescription from '@site/src/components/MemberDescription';


## CustomerGroup

<GenerationInfo sourceFile="packages/core/src/entity/customer-group/customer-group.entity.ts" sourceLine="16" packageName="@vendure/core" />

A grouping of <a href='/typescript-api/entities/customer#customer'>Customer</a>s which enables features such as group-based promotions
or tax rules.

```ts title="Signature"
class CustomerGroup extends VendureEntity implements HasCustomFields {
  constructor(input?: DeepPartial<CustomerGroup>)
  @Column() @Column() name: string;
  @ManyToMany(type => Customer, customer => customer.groups) @ManyToMany(type => Customer, customer => customer.groups)
    customers: Customer[];
  @Column(type => CustomCustomerGroupFields) @Column(type => CustomCustomerGroupFields)
    customFields: CustomCustomerGroupFields;
}
```
Extends

 * <a href='/typescript-api/entities/vendure-entity#vendureentity'>VendureEntity</a>


Implements

 * HasCustomFields



### constructor

<MemberInfo kind="method" type="(input?: DeepPartial&#60;<a href='/typescript-api/entities/customer-group#customergroup'>CustomerGroup</a>&#62;) => CustomerGroup"   />


### name

<MemberInfo kind="property" type="string"   />


### customers

<MemberInfo kind="property" type="<a href='/typescript-api/entities/customer#customer'>Customer</a>[]"   />


### customFields

<MemberInfo kind="property" type="CustomCustomerGroupFields"   />

