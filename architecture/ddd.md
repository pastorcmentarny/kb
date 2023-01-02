## **HONEST WARNING**
**Content in this KB is for me ONLY.**
It contains definitions that explain things in the way that is easiest for me to understand.
_I am not the author of these definitions so check resources section for the origin of definitions._ 


#DDD 
It is acronym for Domain-Driven Design.

**Domain-Driven Design** is one of the most boring thing I read in my IT carrier since DB lectures at university.

**Domain-Driven Design** is all about design and creating highly expressive models.

DDD also aims to create models that are understandable by everyone involved in the software development, not just software developers.

Typically, a model of a domain can be depicted as a UML sketch, as code, and in the language of the domain.

In DDD, it is less about the nouns and verbs and more about the concepts. 

Remember that the language is used to build a representation of the model of the domain. So is the code. When the code is refactored with new terminology then refactor your language to incorporate the new term. 

Strategic design is about design in the large, and helps focus on the many parts that make up the large model, and how these parts relate to each other.
 
#### Bounded Contexts

For each model, deliberately and explicitly define the context in which it exists. it is important thateveryone understands the boundary conditions of the context..

Contexts can be created from (but not limited to) the following:
* how teams are organized
* the structure and layout of the code base
* usage within a specific part of the domain

Aim for consistency and unity inside the context and don't be distracted by how the model is used outside the context. 
Other contexts will have different models, concepts and/or use different dialect

#### Context mapping

Context mapping is a design process where the contact points and translations between bounded contexts are explicitly mapped out. Focus on mapping the existing landscape, and deal with the actual transformations later.

###### *TIP*
&nbsp;&nbsp;&nbsp;&nbsp; *Use continuous integration within a single bounded context to smoothen splinters that arise from different understanding. Frequent code merges, automated tests and applying the ubiquitous language will highlight fragmentation inside the bounded context quickly.*

Within the bounded contexts, effort is focused on building really expressive models; models that reveal the intention more than the implementation.
 
Structure

**Entities** are classes where the instances are globally identifiable and keep the same identity for life. 

**Value objects** are lightweight, immutable objects that have no identity. Value objects are a good place to put complex calculations, offloading heavy computational logic from entities.Value Objects have simple life cycles and can greatly simplify your model.

**Cardinality of Associations** The greater the cardinality of associations between classes, the more complex the structure. Aim for lower cardinality by adding qualifiers.Bi-directional associations also add complexity. Critically ask questions of the model to determine if it is absolutely essential to be able to navigate in both directions between two objects.

**Services**

###### **`_(??? - START)_`**
Sometimes it is impossible to allocate behavior to any single class, be it an entity or value object. These are cases of pure functionality that act on multiple classes without one single class taking responsibility for the behavior. In such cases, a stateless class, called a service class, is introduced to encapsulate this behavior.
###### **`_(??? - END)_`**


#### Application Architecture

Each layer is aware of only those layers below it. As such, a layer at a lower level cannot make a call (i.e. send a message) to a layer above it. 

**User Interface** *Responsible for constructing the user interface and managing the interaction with the domain model. Typical implementation pattern is model-view-controller.*

**Application**	*Thin layer that allows the view to collaborate with the domain.*

**Domain** *An extremely behavior-rich and expressive model of the domain. Note that repositories and factories are part of the domain. However, the object-relational mapper to which the repositories might delegate are part of the infrastructure, below this layer.*

**Infrastructure** *Deals with technology specific decisions and focuses more on implementations and less on intentions. Note that domain instances can be created in this layer, but, typically, it is the repository that interacts with this layer, to obtain references to these objects.*



**Sources**:
- https://dzone.com/refcardz/getting-started-domain-driven


DDD breaks the whole domain model created for the enterprise into subdomains. Each subdomain will have a model, and the scope of that model will be called the bounded context. Each microservice will be developed around the bounded context.