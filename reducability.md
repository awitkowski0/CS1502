# Reducability Notes

## **Quick Facts (T/F Q's)**

## **Notes**

### Reducability 01 - Introduction

1. **Concept of Reducibility:**
   - Reducibility is a method to convert a problem A into another problem B.
   - If a solution to B can solve A, then A is reducible to B.
   - It involves membership problems within sets.

2. **Set Membership and Function:**
   - Consider sets A ⊆ X and B ⊆ Y, with a function f: X → Y.
   - Reducibility is defined as: w ∈ A ↔ f(w) ∈ B.

3. **Logical Equivalence:**
   - P ↔ Q is equivalent to (P → Q) ∧ (Q → P), implying a logical equivalence between A and B through function f.

4. **Problem Conversion:**
   - Problem #1: Determining if a specific element is in set A.
   - Problem #2: Determining if a specific element is in set B.
   - Reducibility allows converting Problem #1 into Problem #2 via function f.

5. **Practical Example:**
   - Using an imaginative scenario involving a sports car's speed and a psychic lady's predictions to illustrate reducibility.
   - The scenario demonstrates converting a problem about a car's speed into a problem about predicting an explosion.

6. **Boolean Algebra Application:**
   - Reducibility is framed in terms of boolean algebra: (P ∧ Q) → R ≡ (¬R ∧ Q) → ¬P.
   - Indicates that if A is undecidable and reducible to B, then B is also undecidable.

7. **Proof of Undecidability:**
   - To prove a language A is undecidable, show that if A is decidable, then another known undecidable problem (e.g., ATM) becomes decidable, leading to a contradiction.
   - This method uses the assumption of decidability and a helper Turing machine to reach a contradiction.

8. **ATM and Reducibility:**
   - ATM (Acceptance Problem for Turing Machines) is a classic undecidable problem.
   - Using ATM in reducibility proofs helps establish undecidability of other problems.

9. **Decidability Transfer:**
   - If B is decidable and a conversion function f exists for A to B, then A is also decidable.
   - Conversely, if A is undecidable and reducible to B, B becomes undecidable.