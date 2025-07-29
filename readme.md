# Bitrix24 E-commerce API Reference

This document provides an overview of the Bitrix24 E-commerce REST API methods organized by functional categories.

## API Methods by Category

| Category | Key Methods | Purpose |
|----------|-------------|---------|
| **Shopping Cart** | `sale.basketitem.*` | Add or update items in the shopping cart; retrieve, list or remove items; add products from the catalog; fetch available cart fields. |
| **Orders** | `sale.order.*` | Create or modify orders; get order details; list or delete orders and related objects. |
| **Payer Types** | `sale.persontype.*` | Manage customer types (individual or legal entity) and their associated properties. |
| **Order Properties & Groups** | `sale.property.*`, `sale.propertygroup.*` | Define fields shown at checkout (e.g., address, phone); group them into logical sections; retrieve or remove properties. |
| **Property Variants & Binding** | `sale.propertyvariant.*`, `sale.propertyRelation.*` | Manage possible values for ENUM properties; bind properties to specific payment systems, delivery services or sales channels. |
| **Order Statuses** | `sale.status.*`, `sale.statusLang.*` | Define and localize order and shipment statuses (e.g., awaiting payment, shipped); update or remove statuses. |
| **Payments** | `sale.payment.*` | Create payment records for orders; modify payment details; retrieve or delete payments. |
| **Payment Systems** | `sale.paysystem.*` | Integrate and configure multiple payment gateways; manage handlers and payment system entities; process payments for orders or invoices. |
| **Linking Payments & Cart Items** | `sale.paymentitembasket.*` | Allocate individual cart items to specific payments when splitting payments between methods. |
| **Linking Payments & Shipments** | `sale.paymentItemShipment.*` | Distribute payment amounts across multiple shipments. |
| **Shipments** | `sale.shipment.*` | Manage shipments for orders; create or modify shipments; retrieve or delete shipments. |
| **Shipment Items** | `sale.shipmentitem.*` | Work with line items within a shipment (product, quantity, price). |
| **Shipment Properties** | `sale.shipmentproperty.*` | Store delivery details such as address, carrier and ship date; manage shipment property definitions. |
| **Cash Registers** | `sale.cashbox.*` | Integrate fiscal cash register devices; configure handlers; register receipts and transmit them to fiscal data operators. |
| **Delivery Services** | `sale.delivery.*` | Add or modify delivery service handlers; manage shipping methods and their configurations; add optional services (insurance etc.); send transport requests. |
| **Product Management** | `catalog.product.*` | Create or modify simple products; retrieve lists or single products; download product files; delete products. |
| **Service Management** | `catalog.product.service.*` | Add or manage non‑inventory services offered in the store. |
| **Parent Products & Variations (SKU)** | `catalog.product.sku.*`, `catalog.product.offer.*` | Support product variations (e.g., size, color) by managing parent products and individual SKUs. |
| **Catalog Sections (Categories)** | `catalog.section.*` | Organize products into sections; link products to multiple categories; manage categories and fields. |
| **Pricing** | `catalog.price.*`, `catalog.priceType.*`, `catalog.roundingRule.*` | Manage product prices and multiple price types (retail, wholesale, partner); add or modify price rounding rules for consistent display. |
| **Units of Measurement & Ratios** | `catalog.measure.*`, `catalog.ratio.*` | Create custom measurement units and ratios (e.g., meters, packs of six) for products. |
| **Margins & VAT** | `catalog.extra.*`, `catalog.vat.*` | Define margins for pricing and set VAT rates for the entire catalog or individual products. |
| **Warehouses & Inventory** | `catalog.store.*`, `catalog.document.*` | Manage warehouses; control stock across multiple locations; add or conduct inventory documents for receipts, adjustments, transfers, returns and write‑offs. |

## Detailed Method Examples

### Shopping Cart Methods
- `sale.basketitem.add` - Add item to cart
- `sale.basketitem.update` - Update cart item
- `sale.basketitem.get` - Get cart item details
- `sale.basketitem.list` - List all cart items
- `sale.basketitem.delete` - Remove cart item
- `sale.basketitem.getFields` - Get available cart fields
- `sale.basketitem.addCatalogProduct` - Add catalog product to cart
- `sale.basketitem.updateCatalogProduct` - Update catalog product in cart

### Order Management Methods
- `sale.order.add` - Create new order
- `sale.order.update` - Update existing order
- `sale.order.get` - Get order details
- `sale.order.list` - List orders
- `sale.order.delete` - Delete order
- `sale.order.getFields` - Get order fields

### Payment System Methods
#### Handlers
- `sale.paysystem.handler.add` - Add payment handler
- `sale.paysystem.handler.update` - Update payment handler
- `sale.paysystem.handler.list` - List payment handlers
- `sale.paysystem.handler.delete` - Delete payment handler

#### Payment Systems
- `sale.paysystem.add` - Add payment system
- `sale.paysystem.update` - Update payment system
- `sale.paysystem.list` - List payment systems
- `sale.paysystem.delete` - Delete payment system
- `sale.paysystem.settings.get` - Get payment system settings
- `sale.paysystem.settings.update` - Update payment system settings
- `sale.paysystem.pay.payment` - Process payment
- `sale.paysystem.pay.invoice` - Process invoice payment

### Delivery Service Methods
#### Handlers
- `sale.delivery.handler.add` - Add delivery handler
- `sale.delivery.handler.update` - Update delivery handler
- `sale.delivery.handler.list` - List delivery handlers
- `sale.delivery.handler.delete` - Delete delivery handler

#### Delivery Services
- `sale.delivery.add` - Add delivery service
- `sale.delivery.update` - Update delivery service
- `sale.delivery.list` - List delivery services
- `sale.delivery.delete` - Delete delivery service
- `sale.delivery.config.get` - Get delivery configuration
- `sale.delivery.config.update` - Update delivery configuration

#### Extra Services
- `sale.delivery.extra.service.add` - Add extra service
- `sale.delivery.extra.service.update` - Update extra service
- `sale.delivery.extra.service.get` - Get extra service
- `sale.delivery.extra.service.delete` - Delete extra service

#### Delivery Requests
- `sale.delivery.request.update` - Update delivery request
- `sale.delivery.request.sendmessage` - Send delivery message
- `sale.delivery.request.delete` - Delete delivery request

### Inventory Management Methods
#### Warehouses
- `catalog.store.add` - Add warehouse
- `catalog.store.update` - Update warehouse
- `catalog.store.get` - Get warehouse details
- `catalog.store.list` - List warehouses
- `catalog.store.delete` - Delete warehouse
- `catalog.store.getFields` - Get warehouse fields

#### Inventory Documents
- `catalog.document.mode.status` - Get document mode status
- `catalog.document.add` - Add inventory document
- `catalog.document.conduct` - Conduct inventory document
- `catalog.document.conductList` - Conduct multiple documents
- `catalog.document.cancel` - Cancel inventory document
- `catalog.document.cancelList` - Cancel multiple documents
- `catalog.document.update` - Update inventory document
- `catalog.document.list` - List inventory documents
- `catalog.document.delete` - Delete inventory document
- `catalog.document.deleteList` - Delete multiple documents
- `catalog.document.getFields` - Get document fields

#### Document Elements
- `catalog.document.element.add` - Add document element
- `catalog.document.element.update` - Update document element
- `catalog.document.element.list` - List document elements
- `catalog.document.element.delete` - Delete document element
- `catalog.document.element.getFields` - Get document element fields
