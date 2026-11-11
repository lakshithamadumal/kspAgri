📌 SECTION 6: Part E – Interpreter Pattern (City Policy DSL) (10:00 – 11:45)
Step 6.1

👉 [තිරයේ කරන්න]: වම් පැත්තේ Navigation Menu එකෙන් "City Policy Rules" tab එක click කරන්න. Header එකේ ඇති "City Policy Rules & DSL Interpreter" සහ "Interpreter Architecture" badge එක Mouse cursor එකෙන් පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"Our final design pattern is Part E: The Interpreter Pattern, powering our Automated Municipal Bylaw and Policy Evaluation Engine. City councils frequently enact dynamic urban regulations—such as commercial noise caps, residential curfews, and environmental zones. If these rules were hardcoded into Java classes, every single policy amendment would require recompiling and redeploying the entire municipal software suite."

Step 6.2

👉 [තිරයේ කරන්න]:

වම් පැත්තේ "Policy Rule Definition" card එක පෙන්වන්න.
Policy Rule Template: dropdown එකෙන්:
👉 Noise Ordinance (Residential dB Limit) තෝරන්න (නැතහොත් default තියෙන එක තබන්න).
පහළ ඇති Expression (Domain-Specific Language): box එකේ:
ZONE == "RESIDENTIAL" AND NOISE_LEVEL > 65
කියන Rule එක Mouse එකෙන් highlight කර පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"To solve this, I designed a Domain-Specific Language (DSL) that parses and evaluates dynamic boolean expressions using an Abstract Syntax Tree. Here, we evaluate a residential noise ordinance: ZONE == 'RESIDENTIAL' AND NOISE_LEVEL > 65 decibels."

Step 6.3

👉 [තිරයේ කරන්න]:

පහළ ඇති Context: ZONE එක RESIDENTIAL ලෙසද, Context: NOISE_LEVEL (dB) අගය 74 ලෙසද පෙන්වන්න.
කොළ පාට ▶ Evaluate Rule Against Context button එක click කරන්න!
දකුණු පස ඇති Parsed Rule Abstract Syntax Tree (AST) card එකේ:
• Terminal Evaluator (ZONE == "RESIDENTIAL") ➔ MATCHED
• Terminal Evaluator (NOISE_LEVEL 74 dB) ➔ EVALUATED
• Root Interpretation Status ➔ VIOLATION DETECTED
පහළින් රතු පාටින් මතු වන POLICY VIOLATION TRIGGERED badge එක Mouse එකෙන් highlight කර පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"Our live municipal sensor context injects a residential zone with a noise reading of 74 decibels. When I click 'Evaluate Rule Against Context', our backend AST parser tokenizes the DSL string and recursively evaluates the syntax tree. Because 74 decibels exceeds the 65 decibel threshold, the root expression evaluates to TRUE, automatically triggering a red 'POLICY VIOLATION TRIGGERED' alert!"

Step 6.4

👉 [තිරයේ කරන්න]:

දැන් වම් පැත්තේ Context: NOISE_LEVEL (dB) කොටුවේ ඇති 74 මකලා 50 (හෝ 65ට අඩු අගයක්) type කරන්න.
නැවතත් කොළ පාට ▶ Evaluate Rule Against Context button එක click කරන්න.
දකුණු පස පහළින් කොළ පාටින් POLICY COMPLIANT (PASS) badge එක මතු වන බවත්, "Current sensor readings are strictly compliant with municipal bylaws" යනුවෙන් update වන බවත් පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"Now, watch what happens when sensor levels drop below the threshold. I update the noise level to 50 decibels and re-evaluate. The Abstract Syntax Tree re-evaluates immediately, returning FALSE and displaying a green 'POLICY COMPLIANT' status. City administrators can formulate and test complex operational bylaws at runtime without altering a single line of backend Java source code."

Step 6.5

👉 [තිරයේ කරන්න]: පහළින් ඇති "Interpreter Pattern Grammar Specification" card එකේ ඇති කොටස් 3 Mouse cursor එකෙන් පෙන්වන්න:

Non-Terminal Expressions (AndExpression, OrExpression)
Terminal Expressions (ComparisonExpression)
Context Environment (CityPolicyContext)
🗣️ [කටින් කියන්න]:

"As detailed in our grammar specification card below, the architecture adheres strictly to Backus-Naur Form: terminal expressions like ComparisonExpression extract contextual sensor metrics, while non-terminal composite expressions like AndExpression recursively evaluate boolean logic against the CityPolicyContext."

Step 6.6

👉 [තිරයේ කරන්න]: IntelliJ IDEA එකට මාරු වී Expression.java, ComparisonExpression.java, AndExpression.java, සහ PolicyDslParser.java tabs පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"In our Java codebase, the Expression interface defines boolean interpret(CityPolicyContext context). The PolicyDslParser constructs the syntax tree using recursive descent parsing, fully demonstrating the GoF Interpreter Pattern."
