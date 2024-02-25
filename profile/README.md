<picture>
    <img alt="Image showing the DFC logo." src="https://www.datafoodconsortium.org/wp-content/uploads/2021/01/cropped-DATAFOODCONSORTIUM_LOGOS-021-e1610371672257.png">
</picture>

# Welcome to the DFC developer space 👋

You have reach the entry point to start working on the [Data Food Consortium project](https://www.datafoodconsortium.org/): a digital commons for producers in short supply chains.

Here you will find all our technical information and resources. All of our work is open source and new contributors are welcome 🤓.

## Get in Touch

You can chat with us on our [Slack workspace](https://app.slack.com/client/T3CKZMVGR/).

To discuss about technical subjects, please use our GitHub discussions.

You can also contact us by [email](mailto:hello@datafoodconsortium.org).

We meet on Zoom, here are a few of our regular working groups:

| Meeting | Description | Language | Date |
| ------- | ----------- | -------- | ---- |
| General | French coordination meeting. General and technical subjects. | French | Bimonthly on Thursday 11h am CET |
| Global Governance | Global coordination meeting, non-technical. | English | 4-weekly on Thursday 12h CET |
| Ontology | Ontology team coordination and updates - technical. | English | Bimonthly on Thursday 15h CET |
| Technical | Technical coordination meeting, covering technical subjects outside of the Ontology. | English | Currently Bimonthly on Monday 17h am CET |


Please contact us through our [Slack workspace](https://app.slack.com/client/T3CKZMVGR/) if you would like more information (or to join) any of the calls.

## Table of contents

- [The big picture](#the-big-picture)
- [Technical prerequisites](#technical-prerequisites)
- [Standard](#standard)
- [Ontology](#ontology)
- [Taxonomies](#taxonomies)
- [Prototype](#prototype)
- [Data model](#data-model)
- [Connector](#connector)
  - [TypeScript](#typescript)
  - [Ruby](#ruby)
  - [PHP](#php)  
  - [Source code generator](#source-code-generator)
- [Working Repositories](#our-working-repositories)

## The Big Picture

The Data Food Consortium (DFC) facilitated data-interoperability between platforms used by producers in short food systems. The end user is able to manage their own data on every DFC compliant platform. For example, when products are sold on one platform, the stock for the same products can be automatically adjusted on every other platforms the producer is selling on. The producer can update all of their data like product information on all DFC platforms, from only one platform.

To make this possible, all the platforms must follow an agreed standard. That is the role of the DFC: provide on open standard to define the way platforms work together. Our standard is itself based on other open standards like RDF, JSON-LD, Linked Data Platform (LDP), and OpenID Connect (OIDC).

The DFC Standard required that the data exposed by the platforms is always data of an authenticated user, who is either the data owner or has explicit consent of the data owner to view/manage data on their behalf.

## Technical prerequisites

As the DFC standard is based on the Semantic Web, a good understanding of [Semantic Web principles](https://www.w3.org/2001/sw/SW-FAQ) is strongly recommended, in particular the notion of [linked data](https://www.w3.org/TR/ldp-primer/).

## Standard

[code](https://github.com/datafoodconsortium/standard) | [issues](https://github.com/datafoodconsortium/standard/issues) |
[PR](https://github.com/datafoodconsortium/standard/pulls) |
[doc](https://datafoodconsortium.gitbook.io/) | [AGPL-3 licence](https://github.com/datafoodconsortium/standard/blob/master/LICENSE)

The DFC standard defines how the DFC compliant platforms must authenticate and exchange data to be able to work together.

To be DFC compliant a platform must:
- authenticate the user with OpenId Connect (OIDC) and provide the received token in requests;
- express the data using the concepts from the DFC's ontology in the JSON-LD format;
- provide Linked Data Platform (LDP) endpoints to access data.

To view a human readable version of our standard please visit our [Gitbook](https://datafoodconsortium.gitbook.io/).

## Ontology

[code](https://github.com/datafoodconsortium/ontology) | [issues](https://github.com/datafoodconsortium/ontology/issues) |
[PR](https://github.com/datafoodconsortium/ontology/pulls) | [doc](https://datafoodconsortium.gitbook.io/dfc-standard-documentation/semantic-specifications) | [AGPL-3 licence](https://github.com/datafoodconsortium/ontology/blob/master/LICENSE)

In order to be interoperable, data exchanged between DFC compliant platforms must be expressed with a common language: the DFC's ontology.

Our ontology expresses concepts like Product, Order, Agent and so on.

To view a human readable representation of our ontology please visit our [ShowVOC server](https://showvoc.datafoodconsortium.org/showvoc/#/datasets/BusinessOntology/data).

## Taxonomies

[code](https://github.com/datafoodconsortium/taxonomies) | [issues](https://github.com/datafoodconsortium/taxonomies/issues) |
[PR](https://github.com/datafoodconsortium/taxonomies/pulls) | [doc](https://github.com/datafoodconsortium/taxonomies) | [AGPL-3 licence](https://github.com/datafoodconsortium/taxonomies/blob/main/LICENSE)

The DFC standard uses [Simple Knowledge Organization System (SKOS)](https://www.w3.org/TR/skos-primer/) taxonomies to reference:
- [Product Types](https://showvoc.datafoodconsortium.org/showvoc/#/datasets/ProductTypes/data) (like vegetable, tomato, cow's milk, dried peas etc);
- [Measures](https://showvoc.datafoodconsortium.org/showvoc/#/datasets/Measures/data) (units, dimensions);
- [Facets](https://showvoc.datafoodconsortium.org/showvoc/#/datasets/Facets/data) (allergens, labels, etc).

You can explore the existing taxons, through our ShowVOC instance [here](https://showvoc.datafoodconsortium.org/showvoc/#/datasets).

To add a new taxon, please open an [discussion](https://github.com/datafoodconsortium/taxonomies/discussions).

## Prototype

[code](https://github.com/datafoodconsortium/prototype) | [issues](https://github.com/datafoodconsortium/prototype/issues) |
[PR](https://github.com/datafoodconsortium/prototype/pulls) | [doc](https://github.com/datafoodconsortium/dfc-prototype-V3/wiki) | [MIT licence](https://github.com/datafoodconsortium/prototype/blob/master/LICENSE)

When a producer uses multiple platforms to manage its products, equivalent data is hosted on multiple platforms. We must be able to express these equivalent relations in order to operate synchronously. A common use case is to update the stock.

Our prototype allows to:
- manage the equivalent links between data hosted on different platforms;
- view and update data on multiple platforms at a time;
- provide a dedicated API to query the equivalent links.

Our prototype is a Proof Of Concept. You can host it by yourself although we provide a managed instance at [proto.datafoodconsortium.org](https://proto.datafoodconsortium.org).

More information can be found on our [wiki](https://github.com/datafoodconsortium/dfc-prototype/wiki).

## Data model

[code](https://github.com/datafoodconsortium/data-model-uml) | [issues](https://github.com/datafoodconsortium/data-model-uml/issues) |
[PR](https://github.com/datafoodconsortium/data-model-uml/pulls) | [doc](https://github.com/datafoodconsortium/data-model-uml) | [AGPL-3 licence](https://github.com/datafoodconsortium/data-model-uml/blob/main/LICENSE)

We have built an Unified Modeling Language (UML) data model in order to generate the source code of our connector.

The UML model can be opened with tools like Eclipse.

## Connector

We have developed a tool called the "connector" to help developers to implement the DFC standard. This tool allows to easily manipulate DFC compliant data and make the exchange of data easier. The connector does not help with authentication nor authorization as this is out of scope and must be handled with dedicated tools.

As all the DFC platforms are not built using the same programming language, we decided to make a source code generator to ease the development and the maintainance of the connector.

We have already produced a TypeScript and a Ruby version of the connector.

### TypeScript

[code](https://github.com/datafoodconsortium/connector-typescript) | [issues](https://github.com/datafoodconsortium/connector-typescript/issues) |
[PR](https://github.com/datafoodconsortium/connector-typescript/pulls) | [doc](https://github.com/datafoodconsortium/connector-typescript) | [MIT licence](https://github.com/datafoodconsortium/connector-typescript/blob/main/LICENSE)

This is the TypeScript version of the connector. You can use it in your platform to implement the DFC standard easier.

It provides:
- TypeScript objects that comply with the DFC ontology (they are mapped). For instance you can create `SuppliedProduct` or `Offer`;
- Functions to easily import data from another platform (supplied in the DFC Standard JSON-LD format);
- Function to easily export data in the DFC standard JSON-LD format.

### Ruby

[code](https://github.com/datafoodconsortium/connector-ruby) | [issues](https://github.com/datafoodconsortium/connector-ruby/issues) |
[PR](https://github.com/datafoodconsortium/connector-ruby/pulls) | [doc](https://github.com/datafoodconsortium/connector-ruby) | [MIT licence](https://github.com/datafoodconsortium/connector-ruby/blob/main/LICENSE)

This is the Ruby version of the connector. You can use it in your platform to implement the DFC standard easier.

It provides:
- Ruby objects that comply with the DFC ontology (they are mapped). For instance you can create `SuppliedProduct` or `Offer`;
- Function to easily export data in the JSON-LD format.

### PHP

[code](https://github.com/datafoodconsortium/connector-php) | [issues](https://github.com/datafoodconsortium/connector-php/issues) |
[PR](https://github.com/datafoodconsortium/connector-php/pulls) | [doc](https://github.com/datafoodconsortium/connector-php) | [MIT licence](https://github.com/datafoodconsortium/connector-php/blob/main/LICENSE)

This is the Php version of the connector. You can use it in your platform to implement the DFC standard easier.

It provides:
- PHP objects that comply with the DFC ontology (they are mapped). For instance you can create `SuppliedProduct` or `Offer`;
- Function to easily import and export data in the JSON-LD format.

### Source code generator

[code](https://github.com/datafoodconsortium/connector-codegen) | [issues](https://github.com/datafoodconsortium/connector-codegen/issues) |
[PR](https://github.com/datafoodconsortium/connector-codegen/pulls) | [doc](https://github.com/datafoodconsortium/connector-codegen) | [AGPL-3 licence](https://github.com/datafoodconsortium/connector-codegen/blob/main/LICENSE)

As all the DFC platforms are not built using the same programming language, we decided to make a source code generator to ease the development and the maintainance of the connector. We are able to generate the connector source code from an UML model thanks to a model-to-text transformer (Acceleo).

This source code generator uses:
- Acceleo: a tool to perform model-to-text transformation;
- An Unified Modeling Language (UML) data model as input.


## Our Working Repositories

| Repository | Discussions | Issues | PR | Licence |
| ---------- | ----------- | ------ | -- | ------- |
| [standard] | [discussions](https://github.com/datafoodconsortium/standard/discussions) | [issues](https://github.com/datafoodconsortium/standard/issues) | [PR](https://github.com/datafoodconsortium/standard/pulls) | [AGPL-3](https://github.com/datafoodconsortium/standard/blob/master/LICENSE) |
| [ontology] | [discussions](https://github.com/datafoodconsortium/ontology/discussions) | [issues](https://github.com/datafoodconsortium/ontology/issues) | [PR](https://github.com/datafoodconsortium/ontology/pulls) | [AGPL-3](https://github.com/datafoodconsortium/ontology/blob/master/LICENSE) |
| [taxonomies] | [discussions](https://github.com/datafoodconsortium/taxonomies/discussions) | [issues](https://github.com/datafoodconsortium/taxonomies/issues) | [PR](https://github.com/datafoodconsortium/taxonomies/pulls) | [AGPL-3](https://github.com/datafoodconsortium/taxonomies/blob/master/LICENSE) |
| [prototype] | [discussions](https://github.com/datafoodconsortium/prototype/discussions) | [issues](https://github.com/datafoodconsortium/prototype/issues) | [PR](https://github.com/datafoodconsortium/prototype/pulls) | [MIT](https://github.com/datafoodconsortium/prototype/blob/master/LICENSE) |
| [business-api] | [discussions](https://github.com/datafoodconsortium/business-api/discussions) | [issues](https://github.com/datafoodconsortium/business-api/issues) | [PR](https://github.com/datafoodconsortium/business-api/pulls) | [MIT](https://github.com/datafoodconsortium/business-api/blob/master/LICENSE) |
| [connector-typescript] | [discussions](https://github.com/datafoodconsortium/connector-typescript/discussions) | [issues](https://github.com/datafoodconsortium/connector-typescript/issues) | [PR](https://github.com/datafoodconsortium/connector-typescript/pulls) | [MIT](https://github.com/datafoodconsortium/connector-typescript/blob/master/LICENSE) |
| [connector-ruby] | [discussions](https://github.com/datafoodconsortium/connector-ruby/discussions) | [issues](https://github.com/datafoodconsortium/connector-ruby/issues) | [PR](https://github.com/datafoodconsortium/connector-ruby/pulls) | [MIT](https://github.com/datafoodconsortium/connector-ruby/blob/master/LICENSE) |
| [connector-php] | [discussions](https://github.com/datafoodconsortium/connector-php/discussions) | [issues](https://github.com/datafoodconsortium/connector-php/issues) | [PR](https://github.com/datafoodconsortium/connector-php/pulls) | [MIT](https://github.com/datafoodconsortium/connector-php/blob/master/LICENSE) |
| [connector-codegen] | [discussions](https://github.com/datafoodconsortium/connector-codegen/discussions) | [issues](https://github.com/datafoodconsortium/connector-codegen/issues) | [PR](https://github.com/datafoodconsortium/connector-codegen/pulls) | [AGPL-3](https://github.com/datafoodconsortium/connector-codegen/blob/master/LICENSE) |
| [data-model-uml] | [discussions](https://github.com/datafoodconsortium/data-model-uml/discussions) | [issues](https://github.com/datafoodconsortium/data-model-uml/issues) | [PR](https://github.com/datafoodconsortium/data-model-uml/pulls) | [AGPL-3](https://github.com/datafoodconsortium/data-model-uml/blob/master/LICENSE) |
