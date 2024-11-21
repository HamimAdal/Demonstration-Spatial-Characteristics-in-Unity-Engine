# Demonstration of the Spatial Characteristics Model (User-Experience Visualization).

**Working Environment.**

--**Software/Game Engine**: Unity

--**Programming**: C#


**Getting Started.**

In a real-world setting, the smart space would be engineered to access and control all the devices within its scope, to support the mechanics for interfacing with the user (or its proxy—a smartphone), and to rely on specialized algorithms designed to ensure rapid and accurate processing of user requests. In this demonstration, we will assume a more abstract perspective.  We will take for granted that the space and the user can interact with each other, and we will assume the availability of algorithms the space uses to satisfy individual user requests. Our goal is simply to illustrate at an abstract level how requests related to a specific <i><a href="https://github.com/HamimAdal/Spatial-Characteristics"> Spatial Characteristics</a></i> can be satisfied by the smart space to deliver the required functionality. 

# Experimental Setup.
To visualize the user-space interactions in the context of the spatial characteristics model, we will employ a virtual space built using the Unity game engine platform, an apartment used to conduct illustrative experiments.  The 3D architectural model captures a real-world apartment consisting of a bedroom, living room, dining space, kitchen, and bathroom. The layout consists of walls, doors, and windows. Furniture, appliances, and other objects were placed at different locations in the space to convey a real-world setting. Smart devices that affect different spatial characteristics will be positioned at various locations as needed. Throughout this section, we assume a single inhabitant of the space.  We further assume that both the user and the smart space share the concept of location.  User requests are location specific while the space has full knowledge of the location for each smart device in the space. Finally, we also assume that, in some circumstances, the space can either measure or estimate the value of a given characteristic at any location in the space while, in other circumstances, it relies on feedback from the user to assess the value of a characteristic at a specific location.

Now, we explore the relation between several representative spatial characteristics, the devices needed to affect their values, and the kinds of heuristics smart spaces may consider employing in order to satisfy user requests.  The goal is to explicate the relation between characteristics, devices, and the space model while offering insights into the engineering challenges associated with building the kind of smart spaces envisioned in terms of Spatial Characteristics.

# Illumination.  

Within an indoor setting, illumination is primarily influenced by artificial smart light fixtures such as light bulbs, lamps, switches, dimmers, etc. It is also affected by natural sources such as sunlight, or external inaccessible sources like streetlights. To deliver a satisfiable outcome, the algorithms need to find the appropriate devices with reasonable configuration, also taking the effects of natural, and inaccessible sources into consideration. Alternatively, smart blinds/windows are also good resources to exploit depending on the weather forecast. The treatment of illumination can become more complex when algorithms start considering the space geometry. The properties of the internal structure dictate the algorithm’s ability to choose among devices. For instance, opaque walls, solid beams, furniture, etc. can obstruct the even distribution of light. The algorithms need to have a clear understanding of space geometry to compensate for such hindrance.

Figure 1 provides a visual representation of how the user pursues a request for the characteristic illumination, and how the space might address and process the request realizing the spatial characteristics model. Our experimental study focused on a combined kitchen-dining space. A typical user-space interaction may assume the user (red sphere has been used as an avatar) to ask for a certain level of illumination at a particular spot, or area, such as in front of the sink. For simplicity, we only used artificial light fixtures with varying capacities distributed at different locations in the virtual space. Six light bulbs were used each having only two settings, on and off.

<table>
  <tr>
    <td>Figure 1: Visualization of spatial characteristics model exercising illumination.</td>
  </tr>
  <tr>
    <td><img src="https://github.com/HamimAdal/Demonstration-Spatial-Characteristics-in-Unity-Engine/blob/main/Figure_demo/illumiantion.png" width=800 height=400></td>
  </tr>
</table>

While the options of heuristics, and search strategies the algorithms might exploit are large and infinite, in our experiment, we conducted a simple demonstration taking the related location of devices into consideration to sort the configuration of devices. The space starts by selecting the light fixture that is nearest to the target location. It continues to perform a linear search through an ordered list of light fixtures prioritizing their minimal distance (heuristic) from the target location into consideration. The search concludes when the desired level has been met by a light fixture or, a set of light fixtures. The background activity of the simulation upon receiving a user request (117 lumens) is illustrated in the bottom left part of Figure 5, where six light fixtures are activated, attempting to achieve the desired level with an accepted threshold of 20 lumens. The final outcome was 104.31 lumens, achieved by device 1 (with brightness level 4) and device 3 (with brightness level 3)

# Temperature.  

https://youtu.be/Iss6uIpqupM (Temperature demonstration in UNITY)

Above link is a demonstration of temperature (implemented in Unity Game Engine) to understand how requests regarding temperature can be realized in smart space in terms of the Spatial Characteristic Model.


In an indoor space, temperature is mainly controlled by smart temperature devices such as HVAC, heater, cooler, floor heating, air conditioner, etc. By nature, temperature is generally distributed uniformly across a specific area. The user can refer to the desired area as an entire enclosed space such as a living room, or a more limited region such as a small area surrounding a couch. Area can also be identified as multiple rooms connected by open doorways or a region that extends across walls. However, it is impractical to consider a sub-area as a desired location of interest that intersects with the walls.

The choice of temperature devices to satisfy a request can vary depending on multiple factors. If the space is built on one centralized air conditioner, then the choice is simple. However, if the space possesses smart HVAC, then it might be a good choice to exploit it to control temperature for a larger region such as an entire room. 

If the area of interest is not a bounded region, but rather a subarea of the room, it makes sense for the space to use devices (upon their availability) that are lower in capacity and closer to the target. As opposed to using smart HVAC, portable smart coolers, and smart heaters can be a good choice in this context as they can restrict the temperature change within the limited region without significantly impacting the surrounding environment outside of the targeted zone. 

Time plays a crucial role in the dynamics of temperature. The thermal transfer rate for each device is a significant factor in determining how much time it may take to realize the temperature’s effect on a desired area. If time is a constraint and considered as an important factor in satisfying a request, the space might need to solve queries differently. For instance, to cool down a room faster, the space can exploit smart fans to spread airflow. Similarly, when the goal is to warm up a room faster, the space can prioritize the floor heating system over the smart heater upon availability if it has a quicker transfer rate. 

Finally, uncontrollable factors can also influence temperature levels in indoor environments. Heavy lighting and prolonged cooking may fluctuate temperature levels although they are not directly related to temperature devices. The space needs to adjust itself against these changes caused by uncontrollable factors.



