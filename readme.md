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
| **Cart Rules & Discounts** | `sale.discount.*`, `sale.coupon.*` | Create and manage promotional rules, discounts, coupons, and cart-based pricing rules; apply conditional discounts based on cart contents, customer groups, or promotional codes. |
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
- `sale.order.getfields` - Get order fields

#### Orders from External Sources
- `sale.orderexternal.add` - Add order from external source
- `sale.orderexternal.update` - Update external order
- `sale.orderexternal.get` - Get external order details
- `sale.orderexternal.list` - List external orders
- `sale.orderexternal.delete` - Delete external order

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

### Product Management Methods
- `catalog.product.add` - Create or add simple products
- `catalog.product.update` - Update existing products  
- `catalog.product.get` - Get product details by ID
- `catalog.product.list` - Retrieve lists of products
- `catalog.product.download` - Download product files
- `catalog.product.delete` - Delete products
- `catalog.product.getFieldsByFilter` - Get product fields by filter criteria

### Catalog Sections (Categories) Methods
- `catalog.section.add` - Add catalog section
- `catalog.section.update` - Update catalog section
- `catalog.section.get` - Get section details
- `catalog.section.list` - List catalog sections
- `catalog.section.delete` - Delete catalog section
- `catalog.section.getFields` - Get section fields

### Pricing Methods
- `catalog.price.add` - Add product price
- `catalog.price.update` - Update product price
- `catalog.price.get` - Get price details
- `catalog.price.list` - List prices
- `catalog.price.delete` - Delete price
- `catalog.priceType.add` - Add price type
- `catalog.priceType.update` - Update price type
- `catalog.priceType.get` - Get price type
- `catalog.priceType.list` - List price types
- `catalog.priceType.delete` - Delete price type

### Units of Measurement Methods
- `catalog.measure.add` - Add unit of measurement
- `catalog.measure.update` - Update unit of measurement
- `catalog.measure.get` - Get measurement unit
- `catalog.measure.list` - List measurement units
- `catalog.measure.delete` - Delete measurement unit

### Additional Sale Methods
#### Basket Properties
- `sale.basketproperty.add` - Add basket property
- `sale.basketproperty.update` - Update basket property
- `sale.basketproperty.get` - Get basket property
- `sale.basketproperty.list` - List basket properties
- `sale.basketproperty.delete` - Delete basket property

#### Trading Platforms
- `sale.tradingplatform.add` - Add trading platform
- `sale.tradingplatform.update` - Update trading platform
- `sale.tradingplatform.get` - Get trading platform
- `sale.tradingplatform.list` - List trading platforms
- `sale.tradingplatform.delete` - Delete trading platform

#### Property Relations & Binding Methods
- `sale.propertyRelation.add` - Add property relation
- `sale.propertyRelation.update` - Update property relation
- `sale.propertyRelation.get` - Get property relation
- `sale.propertyRelation.list` - List property relations
- `sale.propertyRelation.delete` - Delete property relation

#### Property Values Methods
- `sale.propertyvalue.add` - Add property value
- `sale.propertyvalue.update` - Update property value
- `sale.propertyvalue.get` - Get property value
- `sale.propertyvalue.list` - List property values
- `sale.propertyvalue.delete` - Delete property value

### Cart Rules & Discount Management Methods
> **Note**: These methods may not be fully documented in official Bitrix24 API documentation. Availability should be verified with your Bitrix24 instance.

#### Discount Rules
- `sale.discount.add` - Create new discount rule
- `sale.discount.update` - Update existing discount rule
- `sale.discount.get` - Get discount rule details
- `sale.discount.list` - List all discount rules
- `sale.discount.delete` - Delete discount rule
- `sale.discount.getFields` - Get discount rule fields

#### Coupon Management
- `sale.coupon.add` - Create new coupon
- `sale.coupon.update` - Update existing coupon
- `sale.coupon.get` - Get coupon details
- `sale.coupon.list` - List all coupons
- `sale.coupon.delete` - Delete coupon
- `sale.coupon.getFields` - Get coupon fields
- `sale.coupon.activate` - Activate coupon
- `sale.coupon.deactivate` - Deactivate coupon

#### Cart Rule Conditions
- `sale.discount.condition.add` - Add discount condition
- `sale.discount.condition.update` - Update discount condition
- `sale.discount.condition.get` - Get discount condition details
- `sale.discount.condition.list` - List discount conditions
- `sale.discount.condition.delete` - Delete discount condition

#### Promotional Actions
- `sale.discount.action.add` - Add discount action
- `sale.discount.action.update` - Update discount action
- `sale.discount.action.get` - Get discount action details
- `sale.discount.action.list` - List discount actions
- `sale.discount.action.delete` - Delete discount action

## Common Cart Rule Types

### Percentage Discounts
- Fixed percentage off entire cart
- Percentage off specific products or categories
- Tiered percentage discounts based on cart value

### Fixed Amount Discounts
- Fixed amount off entire cart
- Buy X get Y free offers
- Fixed discount on specific products

### Quantity-Based Rules
- Bulk pricing discounts
- Quantity thresholds (buy 3, get 1 free)
- Progressive discounts based on quantity

### Customer-Based Rules
- Customer group discounts
- Loyalty program discounts
- First-time customer promotions
- Repeat customer incentives

### Conditional Rules
- Minimum cart value requirements
- Product combination rules
- Category-specific promotions
- Time-based restrictions (seasonal sales)

### Coupon Types
- Single-use coupons
- Multi-use coupons with limits
- Percentage or fixed value coupons
- Product-specific coupons
- Category-specific coupons

---

**Important Notes:**
1. **API Availability**: All methods listed above are based on the official Bitrix24 REST API documentation. However, availability may vary depending on your Bitrix24 edition (cloud vs on-premise) and subscription plan.
2. **Method Verification**: Before implementing, always verify method availability in your specific Bitrix24 environment using the documentation at https://apidocs.bitrix24.com/
3. **Permission Requirements**: Most methods require specific permissions and scopes. Check the official documentation for required permissions for each method.
4. **Cart Rules and Discount Management**: These APIs may not be fully exposed in all Bitrix24 editions or may require custom development.
5. **Alternative Implementation**: If REST API methods are not available, consider using:
   - Bitrix24 webhooks for cart events
   - Custom business process automation
   - Integration with external promotional engines
6. **Testing Required**: Test API availability in your specific Bitrix24 environment before implementation.
