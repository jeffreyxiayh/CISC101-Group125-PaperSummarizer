Change Log entry - Experimental branch #1: Added "strict" evidence mode and standard warning message, as well as a new section < 50 word edge case
### **Module 3 — Integrator & Checks**

Evidence Modes:

   - evidence_mode = "strict"

     - The summarizer should: 

        - Only include claims, equations, and results that appear in the provided text.

        - If it cannot find enough information, it must say so explicitly (e.g., “The source text does not provide enough detail to summarize this section in strict evidence mode.”).

Apply these **if/else** checks to ensure logical flow and completeness:

  

1. **Missing Section**  

   - If a section is absent → note “Section skipped: no usable text was provided.” in warnings.

  

2. **Empty Text**  

   - If section has no content → note “Section skipped: no usable text was provided.” in warnings.

  

3. **Over-Length**  

   - If summary >200 words → trim and simplify.

  

4. **Terminology Level**  

   - If user is beginner → replace jargon with plain terms.  

   - If expert → retain technical phrasing.


5. **Section length**

  - If section is <50 words → note “Section skipped: no usable text was provided.” in warnings.


6. **Consistency**  

   - Ensure section order matches original paper.  

   - Cross-check glossary terms appear in summaries.
