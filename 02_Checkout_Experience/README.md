## Checkout Experience

This section details the checkout flow, focusing on validation logic, system behavior, and user experience optimization to ensure a seamless and conversion-driven purchase process.

---

### 1. Entry to Checkout

- User clicks "Proceed to Checkout" from cart

**System Behavior:**
- If user is not logged in → redirect to login/signup
- After successful login → redirect back to checkout

---

### 2. Address Selection (Mandatory)

- User must select or add a delivery address

**Validation:**
- "Continue to payment" remains disabled until a valid address is selected

---

### 3. Delivery & Shipping Validation

- System validates serviceability based on delivery location
- Displays available delivery options

**Edge Cases:**
- If location is not serviceable → show error and restrict progression

---

### 4. Coupon Application

Users can apply coupons in two ways:
- Manual entry of coupon code
- Selecting from available coupon list

**Coupon Visibility:**
- Eligible coupons are displayed as active and selectable
- Non-eligible coupons are visible but grayed out

**Eligibility Criteria:**
- Minimum order value
- Product/category applicability
- User eligibility (e.g., new user, first order)
- Expiry date

**System Behavior:**
- Selecting or applying a valid coupon updates pricing instantly
- Attempting to apply an invalid coupon shows an error message
- Only one coupon can be applied at a time

**UX Consideration:**
Displaying both eligible and ineligible coupons improves transparency and encourages users to increase cart value to unlock offers.

---

### 5. Pricing Calculation

The system dynamically updates the final payable amount including:

- Product total
- Discounts (coupons/offers)
- Shipping charges

**Tax Handling:**
- Prices displayed to users are tax-inclusive
- Tax is not shown as a separate line item during checkout
- Detailed tax breakdown is provided in the final invoice

**System Behavior:**
- Pricing updates in real-time based on coupon application and cart changes

---

### 6. Inventory Validation

- Before payment, the system validates stock availability

**System Behavior:**
- If item is out of stock → checkout is blocked and user is notified
- Prevents overselling and order failures

---

### 7. CTA State Management

- "Continue to Payment" is enabled only when:
  - Address is selected
  - All validations are successfully completed

---

### 8. Payment Redirection

- User proceeds to payment gateway after all validations pass

---

### 9. Payment Outcome Handling

**Success:**
- Order is successfully created
- Order ID is generated
- User is redirected to order confirmation page

**Failure:**
- Error message is displayed
- User is given option to retry payment

---

### Key Focus Areas

- Validation-driven progression
- Real-time pricing updates
- Error handling and recovery
- Transparent yet optimized user experience
- Conversion-focused checkout design
