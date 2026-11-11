Minutes
📌 SECTION 1: Introduction & Platform Overview (0:00 – 1:30)
Step 1.1

👉 [තිරයේ කරන්න]: Browser එකේ http://localhost:8080 Dashboard එක Full Screen දමාගෙන Header එකේ ඇති "SmartCity360" ලාංඡනය උඩ Mouse එක තබාගෙන සිටින්න.
🗣️ [කටින් කියන්න]:

"Good day to the respected evaluation panel. My name is Lakshitha Madumal, and my National Identity Card number is 200330800692. Today, I am presenting the system demonstration and architectural defense for the module Object-Oriented Design Patterns II, under assessment code JIAT/OODP II / EX / 01."

Step 1.2

👉 [තිරයේ කරන්න]: Mouse cursor එක Dashboard එක හරහා ගෙනගොස් Navigation Bar එකේ ඇති Tabs 5 (Decorator, Composite, Chain of Responsibility, Flyweight, Interpreter) එකින් එක පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"For this project, I have engineered SmartCity360—an (ත්‍රි හන්ඩන්ඩ් සික්ස්ටි) enterprise-grade municipal IoT and urban governance platform developed with Java 17 and Spring Boot. Modern smart cities face immense challenges in telemetry security, deep administrative hierarchies, rapid grievance resolution, massive IoT memory footprints, and dynamic policy enforcement."

Step 1.3

👉 [තිරයේ කරන්න]: Dashboard එකේ Summary Cards (Metrics / System Status) දිගේ Mouse cursor එක පහළට ගෙනියන්න.
🗣️ [කටින් කියන්න]:

"To address these architectural requirements without tight coupling or scalability bottlenecks, I have implemented five core Gang of Four design patterns: Decorator, Composite, Chain of Responsibility, Flyweight, and Interpreter. Let us now examine each pattern in live execution."

📌 SECTION 2: Part A – Decorator Pattern (Energy Telemetry Security) (1:30 – 3:45)
Step 2.1

👉 [තිරයේ කරන්න]: Navigation Bar එකේ ඇති "Energy Telemetry (Decorator)" tab එක click කරන්න.
🗣️ [කටින් කියන්න]:

"First, we explore Part A: The Decorator Pattern, implemented in our Municipal Smart Energy Telemetry Subsystem. Smart grid meters continuously stream power readings over public networks, requiring modular security layers without altering the underlying transmission streams."

Step 2.2

👉 [තිරයේ කරන්න]: Screen එකේ වම්පස ඇති "Raw Telemetry Stream" කොටුව සහ එහි ඇති Raw JSON Data (Meter ID, Voltage, Current, kWh) Mouse එකෙන් පෙන්වන්න. Checkboxes තුනම (AES-256, HMAC-SHA256, GZIP) unchecked තත්වයේ තබන්න.
🗣️ [කටින් කියන්න]:

"Here on the dashboard, our base component is the EnergyMeterStream, implementing the DataStream interface. Currently, with no security filters applied, it transmits cleartext municipal telemetry containing meter identifiers, voltage, and instantaneous power draw."

Step 2.3

👉 [තිරයේ කරන්න]: කිසිදු checkbox එකක් තෝරන්නේ නැතිව "Secure & Transmit Telemetry" button එක click කරන්න. දකුණු පස payload එකේ plain text එකක් එන බව පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"When transmitted without decorators, the data payload is completely exposed in plaintext, making it vulnerable to interception and spoofing attacks."

Step 2.4

👉 [තිරයේ කරන්න]: දැන් එකින් එක checkboxes 3ම check කරන්න:

[✔] AES-256 Encryption
[✔] HMAC-SHA256 Authentication
[✔] GZIP Compression
🗣️ [කටින් කියන්න]:

"Now, using the Decorator Pattern, we can dynamically wrap our base stream at runtime. We attach three concrete decorators: EncryptionDecorator using AES-256 cipher, AuthenticationDecorator using an HMAC-SHA256 digital signature, and CompressionDecorator using GZIP byte compression."

Step 2.5

👉 [තිරයේ කරන්න]: "Secure & Transmit Telemetry" button එක click කරන්න. දකුණු පස ඇති "Secured Stream Payload" කොටුවේ Base64 Encrypted String එක සහ Signature එක පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"When I click transmit, the decorator chain executes sequentially. The raw data is compressed, encrypted into an unreadable Base64 ciphertext, and cryptographically signed. Notice that the base EnergyMeterStream remains completely untouched, strictly adhering to the Open-Closed Principle."

Step 2.6

👉 [තිරයේ කරන්න]: IntelliJ IDEA එකට මාරු වී (Alt + Tab), DataStream.java, EnergyMeterStream.java, සහ EncryptionDecorator.java files Tabs වලින් open කර කෙටියෙන් පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"In the Java source code, DataStreamDecorator holds a polymorphic reference to DataStream. Each concrete decorator executes its specific task in the readData pipeline before delegating down the chain, allowing any combination of security filters without subclass explosion."

📌 SECTION 3: Part B – Composite Pattern කොම්පසිට් (Municipal Hierarchy) (3:45 – 6:00)
Step 3.1

👉 [තිරයේ කරන්න]: Browser එකට නැවත පැමිණ Navigation Bar එකේ "Municipal Hierarchy (Composite)" tab එක click කරන්න.
🗣️ [කටින් කියන්න]:

"Next, we examine Part B: The Composite Pattern, used to model our Municipal Administrative and Power Distribution Hierarchy. Municipal structures are naturally hierarchical: cities consist of districts, districts contain streets, and streets contain buildings."

Step 3.2

👉 [තිරයේ කරන්න]: Screen එකේ පෙනෙන City Tree එක දිගේ Mouse cursor එක ගෙන යන්න:
Colombo Central Municipal Council ➔ District 01 - Business Hub ➔ Lotus Road ➔ Twin Towers Building A (Leaf).
🗣️ [කටින් කියන්න]:

"As seen in this live tree structure, ZoneComponent serves as the abstract base component declaring uniform methods: shutdownPower, restorePower, and reportUsage. BuildingLeaf represents individual buildings, while ZoneComposite represents intermediate districts that contain collections of child components."

Step 3.3

👉 [තිරයේ කරන්න]: Tree එකෙන් තනි Building එකක් (උදා: Twin Towers Building A) select කර "Shutdown Power" button එක click කරන්න. එහි status එක OFFLINE වන බව පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"When I select an individual leaf node like 'Twin Towers Building A' and trigger 'Shutdown Power', the leaf executes directly, switching its operational status to offline."

Step 3.4

👉 [තිරයේ කරන්න]: දැන් Tree එකේ මුදුනත ඇති Root Node එක වන "Colombo Central Municipal Council" select කර "Restore All Power" button එක click කරන්න.
🗣️ [කටින් කියන්න]:

"Now, watch what happens when I select the root city council composite and trigger 'Restore All Power'. The composite recursively iterates through all nested districts, commercial zones, and individual buildings, restoring power uniformly across the entire city!"

Step 3.5

👉 [තිරයේ කරන්න]: "Report Total Usage" button එක click කර Aggregate Energy Consumption අගය (Total kWh) screen එකේ පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"When invoking reportUsage, each composite aggregates the power draw of all its descendants. The client interacts with individual buildings and entire metropolitan zones identically through clean polymorphism, eliminating complex conditional type checks."

Step 3.6

👉 [තිරයේ කරන්න]: IntelliJ IDEA එකට මාරු වී ZoneComponent.java, ZoneComposite.java, සහ BuildingLeaf.java files open කර code එක පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"In the codebase, ZoneComposite maintains a List<ZoneComponent> and delegates operations recursively. This demonstrates the textbook Composite Pattern where leaf nodes and composite branches are treated uniformly."

📌 SECTION 4: Part C – Chain of Responsibility (Citizen Grievances) (6:00 – 8:00)
Step 4.1

👉 [තිරයේ කරන්න]: Browser එකේ "Citizen Grievances (Chain of Responsibility)" tab එක click කරන්න.
🗣️ [කටින් කියන්න]:

"Moving on to Part C: The Chain of Responsibility Pattern, which powers our Citizen Grievance ග්‍රීවන්සස් Triage Subsystem. In city governance, public complaints range from minor local noise to severe infrastructure emergencies, requiring automated routing without tightly coupling senders to specific municipal departments."

Step 4.2

👉 [තිරයේ කරන්න]: Grievance Form එකේ පළමු Complaint එක ඇතුළත් කරන්න:

Category: NOISE_POLLUTION
Severity: LOW
Description: "Loud music playing in local park after midnight"
ඉන්පසු "Submit Grievance" button එක click කරන්න.
🗣️ [කටින් කියන්න]:

"First, I submit a Low Severity complaint regarding park noise. Watch the processing log: the LocalStaffHandler evaluates the severity, determines it is within its local authority, resolves it immediately, and halts further chain escalation."

Step 4.3

👉 [තිරයේ කරන්න]: Card එකේ Handled By: LocalStaffHandler ලෙස සහ Status: RESOLVED ලෙස දිස්වන බව පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"The resolution is logged in real-time, showing it was resolved at the first tier within a twenty-four-hour service window."

Step 4.4

👉 [තිරයේ කරන්න]: දෙවන Complaint එක ඇතුළත් කරන්න:

Category: WATER_LEAKAGE
Severity: MEDIUM
Description: "Underground main water pipe burst on Galle Road"
ඉන්පසු "Submit Grievance" button එක click කරන්න.
🗣️ [කටින් කියන්න]:

"Next, I submit a Medium Severity water pipe burst. The LocalStaffHandler checks the criteria, finds it exceeds its threshold, and delegates to the FieldSupervisorHandler, which logs the incident and automatically dispatches a specialized technical crew."

Step 4.5

👉 [තිරයේ කරන්න]: තෙවන Complaint එක ඇතුළත් කරන්න:

Category: POWER_GRID_OUTAGE
Severity: CRITICAL
Description: "Central power substation explosion and fire"
ඉන්පසු "Submit Grievance" button එක click කරන්න. Card එකේ Handled By: CityManagerHandler පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"Finally, I submit a Critical electrical substation disaster. The complaint propagates past both local staff and field supervisors until reaching the CityManagerHandler, triggering executive emergency protocols. Each handler either processes the request or delegates to super.handle, achieving true loose coupling."

Step 4.6

👉 [තිරයේ කරන්න]: IntelliJ IDEA එකට ගොස් ComplaintHandler.java, LocalStaffHandler.java, සහ CityManagerHandler.java open කර පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"In code, each handler holds a reference to nextHandler. New approval levels can be added dynamically at runtime without modifying a single line of existing handler logic."

📌 SECTION 5: Part D – Flyweight Pattern (Smart Streetlights Fleet) (8:00 – 10:00)
Step 5.1

👉 [තිරයේ කරන්න]: Browser එකේ "Streetlight Fleet (Flyweight)" tab එක click කරන්න.
🗣️ [කටින් කියන්න]:

"Now let us examine Part D: The Flyweight Pattern, engineered for our Municipal Smart Streetlight Fleet Management Subsystem. In a metropolis managing fifty thousand connected streetlights, instantiating separate heavy objects for every single light exhausts JVM heap memory and triggers severe garbage collection latency."

Step 5.2

👉 [තිරයේ කරන්න]: Screen එකේ ඇති "Deploy 50,000 Streetlights" button එක click කරන්න.
🗣️ [කටින් කියන්න]:

"To eliminate memory bloat, I separated the state into Intrinsic and Extrinsic. I will now trigger the deployment of fifty thousand streetlights across the metropolitan map."

Step 5.3

👉 [තිරයේ කරන්න]: තත්පරයකින් Results load වූ පසු, Screen එකේ ඇති Memory Benchmark Comparison Cards Mouse එකෙන් පෙන්වන්න:

Unoptimized Memory: ~2.40 MB
Flyweight Memory: ~0.098 MB
Reduction Percentage: 95.9% Savings
🗣️ [කටින් කියන්න]:

"Notice the instantaneous JVM runtime benchmark! In a standard unoptimized design, fifty thousand individual objects require approximately 2.40 megabytes of memory. With our Flyweight implementation, memory consumption plummets to just 0.098 megabytes—achieving an extraordinary 95.9% heap memory reduction!"

Step 5.4

👉 [තිරයේ කරන්න]: පහළින් ඇති "Shared Flyweight Pool" table එක පෙන්වන්න (LED-50W, LED-100W, SOLAR-80W යන types 3 පමණක් memory එකේ ඇති බව).
🗣️ [කටින් කියන්න]:

"Here in the flyweight pool, across all 50,000 deployed lights, exactly three shared StreetLightType instances exist in memory. The heavy intrinsic state—wattage, lumen rating, and hardware specs—is shared. The unique extrinsic state—GPS coordinates, pole IDs, and operational status—is passed externally."

Step 5.5

👉 [තිරයේ කරන්න]: IntelliJ IDEA එකට මාරු වී StreetLightType.java, StreetLightFactory.java (ConcurrentHashMap cache), සහ StreetLight.java පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"Looking at StreetLightFactory, it utilizes a thread-safe ConcurrentHashMap cache. If a requested lamp type already exists, it is reused immediately. This guarantees that our municipal IoT infrastructure can scale to millions of connected devices effortlessly."

📌 SECTION 6: Part E – Interpreter ඉන්ටර් ප්‍රිටර් Pattern (City Policy DSL) (10:00 – 11:45)
Step 6.1

👉 [තිරයේ කරන්න]: Browser එකේ "City Policies (Interpreter)" tab එක click කරන්න.
🗣️ [කටින් කියන්න]:

"Our final design pattern is Part E: The Interpreter Pattern, applied to our Dynamic Municipal Environmental Policy Evaluation Engine. City councils frequently update carbon emission caps, pollution rules, and traffic limits. Hardcoding these rules into Java code would require constant recompilation and redeployment."

Step 6.2

👉 [තිරයේ කරන්න]: Preset Rules dropdown එකෙන් Rule එකක් select කරන්න:
(airQualityIndex > 150 AND temperature > 35) OR trafficCongestion == HIGH
Screen එකේ Rule Expression input box එක highlight කර පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"To solve this, I designed a Domain-Specific Language (DSL) that parses and evaluates dynamic boolean expressions using an Abstract Syntax Tree. Here, we define a policy rule: (airQualityIndex > 150 AND temperature > 35) OR trafficCongestion == HIGH."

Step 6.3

👉 [තිරයේ කරන්න]: Current Context Variables boxes පෙන්වන්න:

airQualityIndex = 165
temperature = 38.5
trafficCongestion = HIGH
ඉන්පසු "Evaluate Policy Rule" button එක click කරන්න. Output එකේ EVALUATED: TRUE දිස්වන බව පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"Our current city sensor context reports an air quality index of 165, temperature of 38.5 degrees, and high traffic congestion. When I click 'Evaluate Policy', our AST parser evaluates the expression against the context, returning TRUE and triggering our public health and traffic diversion protocol."

Step 6.4

👉 [තිරයේ කරන්න]: Context එකේ temperature අගය 25 ලෙසත්, trafficCongestion අගය LOW ලෙසත් වෙනස් කර නැවත "Evaluate Policy Rule" button එක click කරන්න. Output එකේ EVALUATED: FALSE එන බව පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"If I dynamically lower the temperature to 25 and set traffic congestion to LOW, the expression re-evaluates immediately to FALSE. Administrators can define and test new municipal policies in real-time without touching any backend Java source code."

Step 6.5

👉 [තිරයේ කරන්න]: IntelliJ IDEA එකට ගොස් Expression.java, ComparisonExpression.java, AndExpression.java, සහ PolicyDslParser.java පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"In the code, Expression defines boolean interpret(CityPolicyContext context). Terminal expressions like ComparisonExpression evaluate attributes, while non-terminal expressions like AndExpression and OrExpression combine sub-expressions recursively to evaluate the syntax tree."

📌 SECTION 7: Test Suite Verification & Conclusion (11:45 – 13:00)
Step 7.1

👉 [තිරයේ කරන්න]: IntelliJ IDEA එකේ පහළින් ඇති Terminal එක හෝ Windows Command Prompt එක open කරගන්න.
🗣️ [කටින් කියන්න]:

"To ensure complete software quality, correctness, and architectural integrity, I implemented an automated test suite using JUnit 5 and Mockito."

Step 7.2

👉 [තිරයේ කරන්න]: Terminal එකේ .\mvnw test (හෝ mvn clean test) type කර Enter ඔබන්න. Tests run වන ආකාරය පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"I will now execute our entire automated test suite from the terminal using Maven: mvn clean test. This executes comprehensive unit and integration tests across all five design pattern modules."

Step 7.3

👉 [තිරයේ කරන්න]: Build එක අවසන් වූ පසු:
Tests run: 27, Failures: 0, Errors: 0, Skipped: 0
[INFO] BUILD SUCCESS
යන කොළ පැහැති output එක Mouse cursor එකෙන් highlight කර පෙන්වන්න.
🗣️ [කටින් කියන්න]:

"As confirmed in the build summary: all 27 automated tests pass with zero failures and zero errors, achieving BUILD SUCCESS across every single pattern implementation."

Step 7.4

👉 [තිරයේ කරන්න]: නැවත Browser එකේ SmartCity360 Dashboard එකට මාරු වී සන්සුන්ව අවසන් කරන්න.
🗣️ [කටින් කියන්න]:

"In conclusion, SmartCity360 proves that the Gang of Four structural and behavioral design patterns provide elegant, scalable, and decoupled architectures for real-world municipal systems. This fully satisfies all technical and academic requirements of the assessment.

Once again, my name is Lakshitha Madumal, National Identity Card number 200330800692.

Thank you very much for your time and evaluation."
