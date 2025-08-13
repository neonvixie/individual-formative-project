# Car price analysis

## Dataset Content
The data used in this project presents different variables associated with different car models, including their price. The raw dataset has 26 categories in total. Here is the brief description of each of the 26 categories contained in it:

1. `Car_ID`: Unique id for each observation (Interger)
2. `Symboling`: Its assigned insurance risk rating, A value of +3 indicates that the auto is risky, -3 that it is probably pretty safe. (Categorical)
3. `CarName`: Name of the car model (Categorical)
4. `fueltype`: Car fuel type i.e gas or diesel (Categorical)
5. `aspiration`: Aspiration used in a car (Categorical)
    - `'std'` refers to a naturally aspirated engine, which means it draws in air at atmospheric pressure without any extra components.
    - `'turbo'` refers to a turbocharged engine, which uses a turbine powered by exhaust gases to force more air into the engine, resulting in more power.
6. `doornumber`: Number of doors in a car (Categorical)
7. `carbody`: body of a car (Categorical)
    - `'convertible'`: A car with a retractable roof that can be a soft top (fabric) or a hardtop (metal).
    - `'hatchback'`: A car with a rear hatch door that swings upward, combining the passenger area and cargo space.
    - `'sedan'`: A car with four doors and a separate, enclosed trunk.
    - `'wagon'`: Similar to a sedan but with an extended roofline that continues over a large cargo area, often with a rear liftgate.
    - `'hardtop'`: A car without a pillar between the front and rear side windows, giving it a more open, airy feel when the windows are down.
8. `drivewheel`: type of a drive wheel (Categorical)
    - `'rwd'` (Rear-Wheel Drive): Power is sent to the rear wheels. This is common in sports cars and trucks.
    - `'fwd'` (Front-Wheel Drive): Power is sent to the front wheels. This is the most common setup for passenger cars.
    - `'4wd'` (Four-Wheel Drive): Power is sent to all four wheels. This is designed for better traction in off-road or slippery conditions.
9. `enginelocation`: Location of the car engine (Categorical)
10. `wheelbase`: Weelbase of a car (Numeric). The distance between the center points of the front and rear wheels. A longer wheelbase generally results in a smoother ride, while a shorter wheelbase can make a car more agile.
11. `carlength`: Length of a car (Numeric)
12. `carwidth`: Width of a car (Numeric)
13. `carheight`: height of a car (Numeric)
14. `curbweight`: The weight of a car without occupants or baggage. (Numeric)
15. `enginetype`: Type of the car engine. (Categorical)
    - `'ohc'` (Overhead Cam): The camshaft is located in the cylinder head. This is the general term for this design.
    - `'dohc'` (Dual Overhead Cam): The most common modern design, with two separate camshafts per cylinder bank—one for intake valves and one for exhaust valves. This allows for better engine breathing and more power.
    - `'dohcv'` (Dual Overhead Cam Valve): Less common variant of DOHC engine.
    - `'ohcv'` (Overhead Cam Valve): This term is similar to OHC but emphasizes that the valves are also located in the cylinder head.
    - `'ohcf'` (Overhead Cam with F-Head): A specific and less common design where the intake valves are in the cylinder head and the exhaust valves are in the block.
    - `'l'`: This likely stands for a L-head engine, an older design where the intake and exhaust valves were located side-by-side in the engine block.
    - `'rotor'`: A rotary engine, which uses triangular rotors to convert pressure into rotational motion instead of pistons.
16. `cylindernumber`: cylinder placed in the car (Categorical). A cylinder is a chamber where fuel is combusted to generate power.
17. `enginesize`: Size of a car (Numeric). This refers to the total volume of air and fuel an engine can draw in during one cycle.
18. `fuelsystem`: Fuel system of a car (Categorical). This is the method used to deliver fuel to the engine's combustion chambers.
    - `'mpfi'` (Multi-Port Fuel Injection): Each cylinder has its own fuel injector, which is the most common modern design.
    - `'spfi'` (Single-Point Fuel Injection): A single injector feeds all cylinders, typically a less efficient system than MPFI.
    - `'spdi'` (Single-Point Diesel Injection): A diesel version of spfi.
    - `'mfi'` (Mechanical Fuel Injection): An older system that uses mechanical pumps and injectors instead of electronic ones.
    - `'idi'` (Indirect Diesel Injection): The fuel is injected into a pre-chamber before entering the main combustion chamber.
    - `'1bbl'`, `'2bbl'`, `'4bbl'`: These refer to carburetor-based systems. bbl stands for "barrel," which is a passageway in the carburetor. More barrels generally allow for more air and fuel to enter the engine, thus more power.
19. `boreratio`: Boreratio of a car (Numeric). The bore-stroke ratio is the ratio of the cylinder's diameter (bore) to the piston's travel distance (stroke). This ratio helps determine how the engine produces power.
20. `stroke`: Stroke or volume inside the engine (Numeric). The distance the piston travels up and down inside the cylinder. This is a critical factor in calculating the engine's displacement.
21. `compressionratio`: compression ratio of a car (Numeric). This is the ratio of the volume inside a cylinder when the piston is at the bottom of its stroke to the volume when the piston is at the top. A higher compression ratio can result in more power and efficiency but may require higher-octane fuel.
22. `horsepower`: Horsepower (Numeric). A measurement of an engine's power output. It tells you how quickly the engine can produce force, which directly relates to a car's top speed and acceleration.
23. `peakrpm`: car peak rpm (Numeric). This stands for Revolutions Per Minute. It is a measure of how fast the engine crankshaft is rotating. Peak RPM is the specific engine speed at which the engine produces its maximum power.
24. `citympg`: Mileage in city (Numeric). It measures fuel economy under typical urban driving conditions, with frequent stops and starts.
25. `highwaympg`: Mileage on highway (Numeric). It measures fuel economy during a consistent, higher-speed drive, like on a highway, without stopping. Highway MPG is almost always higher because a car is more fuel-efficient when it doesn't have to constantly accelerate from a stop.
26. `price` (Dependent variable): Price of a car (Numeric)


## Business Requirements
The aim of this project is to model the price of cars with the available independent variables. It will be used by the management to understand how exactly the prices vary with the independent variables. They can accordingly manipulate the design of the cars, the business strategy etc. to meet certain price levels. Further, the model will be a good way for management to understand the pricing dynamics of a new market. 


## Hypothesis and how to validate?
Based on the dataset, the columns most likely to have a strong correlation with car price are those that describe a car's size, performance, and features. Here is a breakdown of the variables and their likely correlation with price, from strongest to weakest:

##### Strongest Correlation
These variables directly relate to the cost of a car's materials, engineering, and performance.
- horsepower: A car's power output is one of the most significant factors in its price. Higher horsepower generally means a more expensive car.
- enginesize: The physical size of the engine, which is a key determinant of power, is a strong indicator of price. Larger engines are typically more costly.
- curbweight: This is the car's weight without passengers or cargo. Heavier cars often require more materials and a larger engine, making them more expensive. This also correlates with the car's overall size.
- Dimensions (carlength, carwidth, carheight, wheelbase): Larger cars generally cost more to manufacture and are priced higher. The wheelbase, in particular, is a key indicator of a car's size and ride quality.
- drivewheel: The drivetrain type is a major design factor. A specialized system like 4wd (four-wheel drive) is typically more expensive than fwd (front-wheel drive) or rwd (rear-wheel drive).
- aspiration: A turbocharged (turbo) engine is a more complex and expensive component than a standard (std) naturally aspirated engine.
- brand: The manufacturer brand (e.g., Honda vs. Mercedes) is arguably the single most important determinant of price. You'd likely need to extract this from the CarName column.
- carbody: The body style has a significant impact. A luxury sedan or a convertible is typically more expensive than a standard hatchback.

##### Moderate Correlation
These variables are components of the engine that contribute to performance but are not as directly tied to price as the high-level metrics.
- cylindernumber: This is related to enginesize and horsepower. More cylinders generally mean a larger, more expensive engine.
- fuelsystem: The type of fuel injection system affects performance and cost. A modern multi-port fuel injection system (mpfi) is more advanced and often more expensive than an older carburetor-based system (1bbl, 2bbl).
- citympg and highwaympg: Fuel efficiency often has an inverse relationship with price. High-performance, expensive cars tend to have lower MPG, while more affordable economy cars have higher MPG.

##### Weak or No Correlation
These variables are unlikely to have a strong, consistent relationship with a car's price.
- car_ID: This is a unique identifier for each car and has no correlation with any of its properties, including price.
- doornumber: The number of doors has a weak relationship with price. While some two-door sports cars are expensive, so are four-door luxury sedans.
- symboling: This is an insurance risk rating and does not directly relate to the car's market price.

##### Potential indirect correlation
- stroke, boreratio, compressionratio, peakrpm: These are technical engineering details that contribute to performance, but their direct, standalone correlation with the final sale price is often weak. The effects of these are better captured by the more holistic measures of horsepower and enginesize.


## Project Plan
* Outline the high-level steps taken for the analysis.
* How was the data managed throughout the collection, processing, analysis and interpretation steps?
* Why did you choose the research methodologies you used?

## The rationale to map the business requirements to the Data Visualisations
* List your business requirements and a rationale to map them to the Data Visualisations

## Analysis techniques used
* List the data analysis methods used and explain limitations or alternative approaches.
* How did you structure the data analysis techniques. Justify your response.
* Did the data limit you, and did you use an alternative approach to meet these challenges?
* How did you use generative AI tools to help with ideation, design thinking and code optimisation?

## Ethical considerations
* Were there any data privacy, bias or fairness issues with the data?
* How did you overcome any legal or societal issues?

## Dashboard Design
* List all dashboard pages and their content, either blocks of information or widgets, like buttons, checkboxes, images, or any other item that your dashboard library supports.
* Later, during the project development, you may revisit your dashboard plan to update a given feature (for example, at the beginning of the project you were confident you would use a given plot to display an insight but subsequently you used another plot type).
* How were data insights communicated to technical and non-technical audiences?
* Explain how the dashboard was designed to communicate complex data insights to different audiences. 

## Unfixed Bugs
* Please mention unfixed bugs and why they were not fixed. This section should include shortcomings of the frameworks or technologies used. Although time can be a significant variable to consider, paucity of time and difficulty understanding implementation are not valid reasons to leave bugs unfixed.
* Did you recognise gaps in your knowledge, and how did you address them?
* If applicable, include evidence of feedback received (from peers or instructors) and how it improved your approach or understanding.

## Development Roadmap
* What challenges did you face, and what strategies were used to overcome these challenges?
* What new skills or tools do you plan to learn next based on your project experience? 

## Main Data Analysis Libraries
I used `pandas` to read and modify the .csv files. I used `matplotlib`, `seaborn` and `plotly` for data visualization


## Credits 
I use business requirements and the data from the kaggle [Car Price Prediction](https://www.kaggle.com/datasets/hellbuoy/car-price-prediction). I relied heavily on AI (especially Google's Gemini) to understand the dataset content. I also relied on copilot and chatgpt for simple queries and I used it to help me a little bit with the code. I also used a copilot to generate one of the graphs, shich uses sublibraries of plotly that are outside of the course curriculum. 

I also copied a lot of code from a test project I did a day earlier.

### Content 

- The text for the Home page was taken from Wikipedia Article A
- Instructions on how to implement form validation on the Sign-Up page was taken from [Specific YouTube Tutorial](https://www.youtube.com/)
- The icons in the footer were taken from [Font Awesome](https://fontawesome.com/)

### Media

- The photos used on the home and sign-up page are from This Open-Source site
- The images used for the gallery page were taken from this other open-source site