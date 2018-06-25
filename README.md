# What is CurbSpec?
CurbSpec is a data standard for describing urban curb regulations. It exists to help government effectively manage and regulate the curb and to support public and private users of city streets.

CurbSpec is a common language on which many things can be built, including rules engines, query APIs, consumer notification services, mapping tools, and analytic models.

# Design Principles
1. ***Machine-readable:*** From navigation apps to connected cars, urban mobility is increasingly digital. CurbSpec helps computers understand the curb, whether that's answering real-time questions like "where's the nearest place to drop off a passenger?" or modeling parking allocation scenarios for an entire neighborhood.

1. ***Human-oriented:*** Curbs are managed and used by people, so CurbSpec must be useful to humans not just machines. CurbSpec is designed to be directly readable and writable by people with technical training, and to support tools that make it accessible to the non-technical.

1. ***Reversible:*** Most curb management is not digitized today and this won't change overnight. To ease this transition, it must be possible to take existing signs and translate them into CurbSpec, and to use CurbSpec to generate a hypothetical physical signage plan.

1. ***Adaptable:*** No two cities manage their curb in exactly the same way. CurbSpec is built to support many types of regulations and management practices. A city should not have to change its curb regulations to use CurbSpec.

1. ***Future-friendly:*** How we use the curb is changing. Cities are adjusting parking prices based on demand, new transportation services are arriving on our streets, and vehicles without humans behind the wheel will one day deliver people and goods to the curb. CurbSpec exists to help make these futures a reality and will grow and adapt as urban mobility evolves.

# Examples
The pages below show real world curb regulations translated into CurbSpec.

| | |
| :---- | :---- |
| [Examples of Simple Regulations](examples/simple_examples.md) | Simple regulatory scenarios typically involving one or two basic rules  |
| [Examples of Complex Regulations](examples/complex_examples.md) | Complex scenarios that address multiple user classes, complicated expressions of time, and overlapping regulations |

# Data Model
| Object | Description |
| :--- | :--- |
| ***[[Location]]*** | Specifies one or more sections of curb using a linear referencing model [NOT YET DEFINED - Build on existing LR system like [SharedStreets Reference System](https://github.com/sharedstreets/sharedstreets-ref-system)] |
| ***[[Regulation]]*** | A [[Location]] may have one or more regulations that determine what is allowed or forbidden during a particular period of time |
| ***[[Rule]]*** | A [[Regulation]] may have one or more rules that define what particular curb users can and cannot do when the [[Regulation]] is in effect |
| ***[[Timespan]]*** | Defines the time period when a [[Regulation]] is in effect. |
| ***[[UserClass]]*** | Defines a category of curb user. Can be used to denote permit holders, vehicle types, or vehicle function. |

# Future Enhancements
* **External referencing for designated periods**: Extend [[TimeSpan]] to allow arbitrarily designated periods (e.g. "Snow Emergency" or "School Days") to be specifically defined via a static or dynamic (API) referencing system.

* **Enhanced payment definition**: A schema to define payment requirements for a given use. Could support the publishing of dynamic parking pricing or complex fee structures such as peak period ride share pickup / drop-off fees.

* **Cross-jurisdictional allowed use mapping**: A mechanism to translate [[Rules|Rule]] (which are locally defined in their meaning) into a standardized, cross-jurisdictional list of activities. This would, for example, allow automated interpretation of local rules to determine where activities like passenger loading could take place.