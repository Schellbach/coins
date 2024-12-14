# Coin Standard BIP

Redefinition of the Base Denomination to Coin

**Abstract**

This BIP proposes to reinforce the commonly recognized "bitcoin" unit so that what was previously known as the smallest indivisible unit becomes the primary reference unit. Under this proposal, one bitcoin is defined as that smallest unit, eliminating the need for decimal places. By making the integral unit the standard measure, this BIP aims to simplify user comprehension, reduce confusion, and align on-chain values directly with their displayed representation.

**Motivation**

The current convention defines one BTC as 100,000,000 satoshis. This representation requires dealing with eight decimal places, which can be confusing and foster the misconception that bitcoin is inherently decimal-based. In reality, Bitcoin’s ledger represents values as integers of a smallest unit, and the decimal point is merely a human-imposed abstraction.

By redefining the smallest unit as "one coin," this BIP aligns user perception with the protocol’s true nature. It reduces cognitive overhead, ensures users understand Bitcoin as counting discrete units, and ultimately improves educational clarity and user experience.

**Specification**

Redefinition of the Unit:
Internally, the smallest indivisible unit remains unchanged.

Historically, 1 BTC = 100,000,000 base units, or satoshis. Under this proposal, "1 coin" equals that smallest unit.

1 BTC = 100,000,000 coins

What was previously referred to as "1 BTC" now corresponds to 100 million coins under the new definition.

Terminology:
The informal terms "satoshi" or "sat" are deprecated.
All references, interfaces, and documentation SHOULD refer to the base integer unit simply as "coin."

Display and Formatting:
Applications SHOULD present values as whole integers without decimals.

Example:
Old display: 0.00010000 BTC
New display: 10000 coins (or ¢10000)

Conversion:
Ledger and consensus rules remain unchanged.
Implementations adopting this standard MUST multiply previously displayed BTC amounts by 100,000,000 to determine the new integer representation.

**Rationale**

Usability:
Integer-only displays simplify mental arithmetic and reduce potential confusion or user error.

Protocol Alignment:
The Bitcoin protocol inherently counts discrete units. Defining coins as the smallest unit aligns user perception with Bitcoin’s actual integral design.

Educational Clarity:
Presenting integers ensures newcomers do not mistakenly assume that Bitcoin’s nature is decimal-based. It conveys Bitcoin’s true design from the start.

Benefits of this BIP:

1. Future-Proof:
Adopting the smallest unit as the primary measure ensures a consistent standard that can scale smoothly as Bitcoin adoption grows.

2. Persistent Mindset:
Using "coins" retains a layered decimal approach, allowing users to continue thinking in terms of stacking a subunit to earn bitcoin (BTC and coins). This reduces complexity.

3. Flexible User Experience:
Users can toggle between BTC for large amounts and coins for small amounts. Given existing heuristics, coins creates a unified view of value, it unifies the user experience.

4. Alignment with the Protocol’s Nature:
The "coins" proposal aligns the displayed value with the integral nature of Bitcoin’s ledger while continuing to provide fractional units. Using "coins" embraces the fundamental integer-based accounting that Bitcoin employs.

In essence this BIP attempts to simplify small amount representations, it only replaces confusing protocol origin explainations with intuition. By redefining "coins" as the smallest indivisible unit, this BIP embraces reliance on decimal fractions and reinforces stacking and coin memetics, offering a clearer, more intuitive, and ultimately more durable solution.

**Backward Compatibility**

No consensus rules are altered, and on-chain data remains unchanged. Differences arise solely in display formats:

For Developers:
Update GUIs, APIs, and documentation to present values as "coins". Remove references to sats or satoshis.

For Users:
The actual value of holdings does not change. Transitional measures, such as dual displays or explanatory tooltips, can ease the adjustment period.

**Security Considerations**
A short-term risk of confusion exists as users adapt to the new representation. Users accustomed to satoshis may misinterpret initial displays. To mitigate this:
Offer dual displays and tooltips during the transition.

Provide clear educational materials and coordinated messaging.

Use alerts or confirmations in applications if input values appear unexpectedly large or small.

Over time, confusion will subside, leaving a simpler, more intuitive understanding of Bitcoin’s integral values.

**Reference Implementation**

Some wallets, such as Coinward, showcase integer-only displays, demonstrating the feasibility of this approach. Transitional features—like showing both old and new formats side-by-side—can help smooth the transition.

**Test Vectors**

Old: 1.00000000 BTC → New: 100,000,000 coins (or ¢100000000)
Old: 0.00010000 BTC → New: 10,000 coins (or ¢10000)
Old: 0.00500000 BTC → New: 500,000 coins (or ¢500000)

All formerly fractional representations now directly correspond to whole-number multiples of the smallest unit.

**Implementation Timeline**

Phase 1 (1-3 months): Introduce the concept, provide dual displays and educational materials.

Phase 2 (3-6 months): Prominent services adopt integer-only displays by default.

Phase 3 (6+ months): Integer representation becomes standard. Documentation and user guides no longer reference decimal-based formats.
**Conclusion**

Redefining the "coin" unit as the smallest indivisible unit and removing decimal-based representations simplifies comprehension and aligns displayed values with the protocol’s integral accounting. While a transition period may be necessary, the long-term benefits include clearer communication, reduced confusion, and a more accurate understanding of Bitcoin’s fundamental design.

**Copyright**

This BIP is licensed under CC0-1.0.
