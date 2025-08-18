# Gas, Graphs & Gears: Visualizing Trade-Offs in Car Design with D3

This project uses D3.js to visualize trade-offs in car design from the late 1970s to early 1980s, highlighting the inverse trends between fuel efficiency and engine power following the oil crisis.

## Narrative Visualization URL
[https://kesavar-kabilar.github.io/GasGraphsGears/](https://kesavar-kabilar.github.io/GasGraphsGears/)

## Messaging

The main purpose of this narrative visualization is to showcase how the efficiency and power were incorporated into manufacturing cars from the early 1970s to the early 1980s. It specifically compares the efficiency (measured by miles per gallon) in relation to the power (measured by horsepower). This aims to show how the car industry was influenced by historical events, such as the oil crisis, which led to a change for automotive industries to prioritize efficiency over power. This change can be observed by utilizing a scatterplot of each car’s performance data from the early 1970s, late 1970s, and the early 1980s. By analyzing the trends across these distinct periods, it can be observed that the cars’ performances are moving towards the top left, indicating that the manufactured cars were becoming more efficient (higher miles per gallon) and had lesser horsepower (fewer values for horsepower). This indicates that horsepower became less prioritized, and efficiency was more valued and significant in the design and production of upcoming vehicles.

## Narrative Structure

This narrative visualization is designed to follow an interactive slideshow. Each scene presents a specific snapshot of cars’ performances during particular time periods.

* The first scene represents the **Early 1970s: The Era of Muscle Cars**.
* The second scene represents the **Late 1970s: The Oil Crisis Impact**.
* The third scene represents the **Early 1980s: Further Efficiency Gains**.

The user can click through the "Previous" and "Next" buttons to navigate and explore the 3 time periods and observe the overall shift from all the car performances. This provides a clear, linear progression through the story, guiding the viewer from one key insight to the next.

While the main purpose is to show the overall trend of the cars’ performances through the 3 time periods, the viewer can also use a "drill-down" opportunity within each slide through the use of interactive tooltips. Users can hover over individual data points (cars) on the scatterplot to explore specific details like the car name, exact MPG, horsepower, and model year. This allows for deeper, on-demand exploration of individual data points without disrupting the main narrative progression or forcing the viewer into a new branch of the story.

## Visual Structure

This narrative visualization is designed with a scatterplot for each scene. This choice ensures the viewer can effectively understand the data and navigate the scene by clearly mapping two quantitative variables: horsepower on the x-axis and miles per gallon (MPG) on the y-axis. The use of labeled axes ("Horsepower" and "Miles Per Gallon (MPG)") provides clear navigation within the data space, allowing viewers to quickly grasp the relationships between these two metrics for individual cars.

To highlight important parts of the data and urge the viewer to focus on key insights within each scene, the visualization employs explicit annotations. The viewer also has the ability to click next and previous to move to the next scene or the previous scene. The visualization facilitates smooth transitions between scenes and helps the viewer understand how the data connects across different time periods through data constancy and animation. By maintaining consistent axes and scales throughout the scenes, a stable visual base is established, enabling clear observation of shifts in the data points.

## Scenes

The first scene, titled "Early 1970s: The Era of Muscle Cars," displays the performance data of several cars from 1970 to 1974 (inclusive). In this initial view, the scatterplot reveals several cars that are geared towards the lower-right quadrant, indicating a large number of vehicles with higher horsepower but relatively lower miles per gallon. This visual trend showcases the automotive priorities of the time, where raw power and larger engines were often favored, leading to less fuel-efficient designs. It also shows some cars towards the bottom left quadrant, showing a lower horsepower and lower efficiency likely from imported cars. Annotations in this scene would specifically highlight these clusters, drawing the viewer's attention to the characteristics defining this era.

The second scene, titled "Late 1970s: The Oil Crisis Impact," displays the performance data of several cars’ from 1975 to 1979 (inclusive). This period showcases the after-effect of the oil crisis. After this oil crisis, it showcased the potential of oil becoming very scarce and efficiency of a car becoming more important. While some high-horsepower, low-MPG vehicles were still present, the scatterplot shows that most cars were starting to prioritize lower horsepower and higher efficiency. Annotations here would guide the viewer to perceive the initial responses of the automotive industry to the increased demand for fuel economy.

The third scene, titled "Early 1980s: Further Efficiency Gains," displays the performance data of several cars’ from 1980 to 1982 (inclusive). In this final scene, the scatterplot shows a more pronounced shift towards higher MPG, with many data points in the top left quadrant, especially for lower and medium horsepower ranges. This scene vividly illustrates the advancements in fuel efficiency driven by continued consumer demand and potentially stricter regulations following the energy crises. Annotations emphasize the main priority of efficiency where cars achieve much higher MPG with relatively lower horsepower, cementing the narrative of how efficiency became a dominant and significant factor in car design and production.

## Annotations

The annotations in this narrative visualization are used to show specific messages in specific areas of the scatter plots. These annotations are used to explain specific behaviors in the graph as to why specific patterns can be seen on the graph.

Annotations are used to elaborate on certain messages to further indicate the observed patterns that lead to the main message, that efficiency becomes more relevant than horsepower. This is done by:

* Highlighting specific data clusters: For example, in the initial scene depicting the early 1970s, annotations explain the groups of cars that exhibit a combination of high horsepower and low fuel efficiency, thereby visually emphasizing the "muscle car era."
* Explaining observed trends: As the narrative progresses through different time periods, annotations indicate the changing patterns, such as the overall shift towards improved Miles Per Gallon.
* Reinforcing the scene's central message: By offering additional context to the current historical period, annotations work to solidify the viewer's understanding of the shift from prioritizing horsepower to prioritizing efficiency.

The annotations change with the change of each scene. When the user navigates from one scene to the next using the "Previous" or "Next" buttons, the annotations from the previous scene are entirely cleared from the display, and a fresh set of annotations for the newly loaded scene is presented. This method ensures that only pertinent information is visible at any given moment, maintaining focus and preventing unnecessary visual information overload.

## Parameters

The parameters of this narrative visualization are the variables that are used to display the current state and visual output. These parameters include:

1.  `currentSceneIndex` (Integer variable): This integer variable represents the current scene and the index of the scenes array. It directly correlates to the specific scene from the scenes array, which is later used to display the visual output of the current scene.
2.  `scenes` (array): This array holds distinct objects, with specific necessary information for each individual scene. Each scene object contains sub-parameters such as the title (for the scene's heading), a filter function (to only select the relevant data points), and annotations (to provide the proper text for each annotation).
3.  `allCarData` (array): This array holds the entire dataset. It holds all the raw car performance information, which is later filtered by the specific scene.

The states of the narrative visualization are entirely determined by the value of the `currentSceneIndex`. Each unique value of this index corresponds to a distinct narrative state, representing a particular time period in the car efficiency story (Early 1970s, Late 1970s, Early 1980s). These parameters are used to construct each scene through the `drawScene` function. When the `drawScene` function is called with a specific `currentSceneIndex`, it accesses the corresponding scene's parameters (title, filter, annotations) from the scenes array. These parameters then guide the function in drawing the scatterplot with the correct data points, titles, and annotations, thereby presenting the correct visual graph of the user-specified narrative state.

## Triggers

This narrative visualization uses triggers to allow the user to freely explore the intricacies of the data. In this narrative visualization, the user can explore through 3 main features: the previous button, the next button, and the mouse over feature.

1.  **Previous Button Click**: This allows the user to progress to the preceding scenes. As an example, from the early 1980s, if the user wants to traverse to the previous scenes, the user can click the previous button, allowing the viewer to navigate to the late 1970s or the early 1970s. This provides the viewer with control over their own custom speed of the story, enabling them to discover and visualize the evolving patterns at their own discretion.
2.  **Next Button Click**: This allows the user to progress to the next scenes. As an example, if the user is currently viewing the early 1970s scene and wants to see the impact of the oil crisis, they can click the "Next" button to navigate to the late 1970s scene. This provides the viewer with control over their own custom speed of the narrative, enabling them to discover and visualize the evolving patterns at their own discretion.
3.  **Mouseover on Data Point (Circle)**: This allows the viewers a "drill-down" opportunity, allowing the user to explore specific information of individual cars on demand. The viewer can hover over a data point to instantly access detailed information such as the name of the car, car’s miles per gallon, car’s horsepower, and the car’s model year. This allows the viewer the ability to get specific information of the data without disrupting the narrative flow of the scene.

In addition, the scene-indicator displays the total number of scenes and the current scene. By displaying "Scene X of Y" (e.g., "Scene 1 of 3"), it continuously shows the user their current position within the narrative sequence and the total number of scenes available, providing a clear sense of progression and scope.
