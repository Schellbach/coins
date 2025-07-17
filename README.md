# Coin Standard BIP

Redefinition of the Base Denomination to Coin

**Abstract**

This BIP proposes redefining the commonly recognized "satoshi" unit so that bitcoin's base unit becomes the primary reference unit and reinforces monetary value associations. Under this proposal, one coin is defined as that smallest unit, largely eliminating the need for decimal places while appealing to common intuition. By making the integral unit the standard measure, this BIP aims to simplify user comprehension, reduce confusion, better leverage existing unicode symbols, and align on-chain values directly with their displayed representation.

**Motivation**

Bitcoin's current terminology centers on "BTC" as the primary unit. While "satoshis/sats" offer integer simplicity for small transactions, they remain secondary and require explanation to newcomers to avoid confusion.

By replacing "satoshi/sats" with "coins" we unify how we talk about Bitcoin, and make it easier for users to intuitively grasp accumulation, scarcity, and everyday utility. Newcomers and even veterans juggle terms like "BTC," "sats," and decimals, complicating education, adoption, and seamless integration into finance tools.

By establishing "coin" as the base unit (where 1 BTC = 100,000,000 coins), this BIP positions "coin" as the main way to discuss and display Bitcoin values. This replaces decimal formats with straightforward integer expressions across wallets, exchanges, and media—fostering a consistent understanding. The Coin Standard BIP simplifies formatting, enhances memetic appeal for viral adoption, and reinforces Bitcoin's finite supply of 2.1 quadrillion coins, or 21 million bitcoins, all without altering the protocol.

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
Adopting the "¢" symbol for coins reinforces monetary value and gives bitcoin subunits the _centlike_ association originally intended for satoshis/sats.

Example:
Old display: 0.00010000 BTC
New display: 10000 coins (or 10000¢)

Conversion:
Ledger and consensus rules remain unchanged.
Implementations adopting this standard MUST multiply previously displayed BTC amounts by 100,000,000 to determine the new representation in coins.

**Rationale**

Usability:
Integer-only displays simplify mental arithmetic and reduce potential confusion or user error.

Protocol Alignment:
The Bitcoin protocol inherently counts discrete units. Defining coins as the smallest unit aligns user perception with Bitcoin’s actual integral design.

Educational Clarity:
Presenting values in coins ensures newcomers do not mistakenly assume that Bitcoin’s too expensive or unattainable for them. This presentation defeats unit bias for newcomers from the start. 

Benefits of this BIP:

1. Future-Proof:
Adopting the smallest unit as the primary measure ensures a consistent standard that can scale smoothly as Bitcoin adoption grows.

2. Persistent Mindset:
Using "coins" retains a layered decimal approach, allowing users to continue thinking in terms of stacking a subunit to earn bitcoin (collect 100,000,0000 coins for a "whole bitcoin"). This builds on the existing understanding while reducing friction from unit bias.

3. Flexible User Experience:
Users can toggle between bitcoin(₿) for large amounts and coins(¢) for small amounts. Given existing heuristics, coins creates a unified view of value, it unifies the user experience.

4. Alignment with the Protocol’s Nature:
The Coin Standard aligns the displayed value with the integral nature of Bitcoin’s ledger while continuing to provide fractional units. Using "coins" embraces the fundamental integer-based accounting that Bitcoin employs.

In essence this BIP attempts to simplify small amount representations, it replaces confusing protocol origin explainations with intuition. By redefining "coins" as the smallest indivisible unit, this BIP embraces existing knowledge of subunits and reinforces stacking and coin memetics, offering a clearer, more intuitive, and ultimately more durable solution.

**Backward Compatibility**

No consensus rules are altered, and on-chain data remains unchanged. Differences arise solely in display formats:

For Developers:
Update GUIs, APIs, and documentation to present values as "coins". Remove references to sats or satoshis.

For Users:
The actual value of holdings does not change. Transitional measures, such as dual displays or explanatory tooltips, can ease the adjustment period.

**Security Considerations**
A short-term risk of confusion exists as users adapt to the new representation. Users accustomed to satoshis may misinterpret initial displays. There may be confusion between 1 bitcoin and 1 coin at the beginning. To mitigate this:
Offer dual displays and tooltips during the transition.

Provide clear educational materials and coordinated messaging.

Use alerts or confirmations in applications if input values appear unexpectedly large or small.

Over time, confusion will subside, leaving a simpler, more intuitive understanding of Bitcoin’s integral values.

**Reference Implementation**

Some wallets, such as Coinward, showcase integer-only displays, demonstrating the feasibility of this approach. Transitional features—like showing both old and new formats side-by-side—can help smooth the transition.

**Test Vectors**

Old: 1.00000000 BTC → New: 100,000,000 coins (or 100000000¢)
Old: 0.00010000 BTC → New: 10,000 coins (or 10000¢)
Old: 0.00500000 BTC → New: 500,000 coins (or 500000¢)

All formerly fractional representations now directly correspond to whole-number multiples of the smallest unit.

**Implementation Timeline**

Phase 1 (1-3 months): Introduce the concept, provide dual displays and educational materials.

Phase 2 (3-6 months): Prominent services adopt integer-only displays by default.

Phase 3 (6+ months): Integer representation becomes standard. Documentation and user guides no longer reference decimal-based formats.
**Conclusion**

Redefining the "coin" unit as the smallest indivisible unit and removing decimal-based representations simplifies comprehension and aligns displayed values with the protocol’s integral accounting. While a transition period may be necessary, the long-term benefits include clearer communication, reduced confusion, and a more accurate understanding of Bitcoin’s fundamental design.

**Copyright**

This BIP is licensed under CC0-1.0.
