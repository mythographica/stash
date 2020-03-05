# Inheritance in JavaScript : Factory of Constructors with Prototype Chain : point of view from boring nerd

<img src="https://dev-to-uploads.s3.amazonaws.com/i/gguiu7k8jqsu3jf2hx5n.png" align="right"/>

Hello fellow Stranger!


This story is about one very special part of JavaScript, the [most usable](https://githut.info/) artificial language in the world for now (2019).

---

IMO no doubt [Brendan Eich](https://en.wikipedia.org/wiki/Brendan_Eich), the author of JavaScript programming language, is an Outstanding Genius! And this is not because he says:

> “ [Always bet on JavaScript](https://brendaneich.com/) ”

This story is some sort of philosopher sight on Inheritance in JavaScript and my hope this vision might be based on the most relevant source of knowledge: Life itself, in it’s creatures and creations. I don’t know if it was source of vision for JavaScript Prototype Chain, though if so, this means is so impacting, so strong for me, that… it is hard to even breath…

**_Let start_** and our first point is where we Switch On our Imagination and try to get rid of all circumstances, prepositions and other irrelative side-effects.

**_We going_** [**_back to the future_**](https://en.wikipedia.org/wiki/Back_to_the_Future) **_of early pre Internet Era of 199x._**

Starting from the first [Hackers](https://en.wikipedia.org/wiki/Hackers:_Heroes_of_the_Computer_Revolution) who invented everything we know of software, we then can see this Picture from the past: [Netscape Navigator](https://en.wikipedia.org/wiki/Netscape_Navigator) 2 in a war run with [Internet Explorer](https://en.wikipedia.org/wiki/Internet_Explorer) 3. [Java](https://en.wikipedia.org/wiki/Java_%28programming_language%29) is just born and almost all, almost everything of current Internet is not yet invented and then might be re-discovered. Might also be as me you were young enough for that Good Old Times, and you can still remember this terrific feelings of how everything is crafted nearby You.

So, with yous very powerful PC based on [Intell Pentium 200 MMX™](https://ark.intel.com/content/www/us/en/ark/products/49966/intel-pentium-processor-with-mmx-technology-200-mhz-66-mhz-fsb.html) inside and 32Mb memory and Windows 3.11 or even Windows 95 is onboard you are looking forward. And you also have both of that [Web Browsers](https://en.wikipedia.org/wiki/Web_browser) installed. [Dial-Up](https://en.wikipedia.org/wiki/Dial-up_Internet_access) modem allows you to connect to the Global Network for grabbing some new data, learning, chatting and so on. However stop, no chatting throught web-pages yet, because JavaScript is still not made. Probably you use some delayed messaging systems, might be based on [EMail](https://en.wikipedia.org/wiki/Email) or [UseNet](https://en.wikipedia.org/wiki/Usenet) or even something like realtime communication technics with [IRC](https://en.wikipedia.org/wiki/Internet_Relay_Chat).

Couple of years gone, and Everything changed… Now you can see animations of snowflakes on web-pages, celebrating Christmas or New Year. And you wonder how it was done, and you able to find there is a new technology inside, called JavaScript language. [HTML](https://en.wikipedia.org/wiki/HTML) is not so new for you, and you start learning that awesome and sparkling tech. Also somehow you then discover [CSS](https://ru.wikipedia.org/wiki/CSS), and this is also important, cause indeed everything is done through combining three of them together. 

>Wow.

And you also might see some wonderful changes for your Windows, you can now create your first application using [CScript](https://en.wikipedia.org/wiki/Windows_Script_Host) or even [HTA](https://en.wikipedia.org/wiki/HTML_Application) (still works).

You start crafting your first Web Server, using [Perl](https://en.wikipedia.org/wiki/Perl), or [C](https://en.wikipedia.org/wiki/C_%28programming_language%29)~[C++](https://en.wikipedia.org/wiki/C%2B%2B), might be even some [bash](https://en.wikipedia.org/wiki/Bash_%28Unix_shell%29) scripting if you start using [Unix-like](https://en.wikipedia.org/wiki/Unix-like) [OS](https://en.wikipedia.org/wiki/Operating_system). And everything is bound between with [Common Gateway Interface](https://en.wikipedia.org/wiki/Common_Gateway_Interface) (not that another [CGI](https://en.wikipedia.org/wiki/Computer-generated_imagery)). [PHP](https://en.wikipedia.org/wiki/PHP) is almost not exists yet, and you will probably like it then.

200x Era. You can now use [JScript](https://en.wikipedia.org/wiki/JScript) on server with [ASP](https://en.wikipedia.org/wiki/Active_Server_Pages). It looks like very similar to JavaScript you use for your web pages. It is so great. You think of your own [template engine](https://en.wikipedia.org/wiki/Template_engine), some sort of [XML](https://en.wikipedia.org/wiki/XML). And then someone named as [AJAX](https://en.wikipedia.org/wiki/Ajax_%28programming%29) all that [Dynamic](https://en.wikipedia.org/wiki/Dynamic_HTML) Content Loading techniques you’ve been using for years before. And they do only [XMLHTTPRequest](https://developer.mozilla.org/en-US/docs/Web/API/XMLHttpRequest) for everything, wile you can still think of [BMP](https://en.wikipedia.org/wiki/BMP_file_format), [iframe](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe), or even [`<script>`](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/script) tag. And then someone hinted about JSON and how it very pleasant to use it, but you were using it _for ages_ in from of:

```javascript
		document.write("<" + "script src=" + path + ">");
```

It is all not that matter **_now_**, but you still can remember **_how_**…

Then from time to time you might been working with [Rhino](https://developer.mozilla.org/en-US/docs/Mozilla/Projects/Rhino) and [Nashorn](https://en.wikipedia.org/wiki/Nashorn_%28JavaScript_engine%29) in an attempt to enjoy your Java customers who use [Alfresco](https://www.alfresco.com/) or [Asterisk](https://www.asterisk.org/). You’ve heard about upcoming JS implementations on hardware chips and wonder what would it be. Also now there is [jQuery](https://jquery.com/) and [Backbone](https://backbonejs.org/).

Then you are looking on a winter snow of upcoming 2010, and now you know there is a Game Changer number One: [Node.js ®](https://nodejs.org/en/). Next ten years you will play with this new toy, and here in 2019 you still can’t believe how great is it.

In general you are enjoying all of that and toys and playing games with them is a great part of your life interests.

---

**_But there is one small question, you ask yourself from day to day, from night to night for more than two decades:_**

> **How will you explain** [**Empathy**](https://en.wikipedia.org/wiki/Empathy) **in JavaScript?**

You know one of the hardest topics about JavaScript is of it’s [Inheritance system and Prototype Chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain). You love it, you can explain how it works, because you’ve learned it from very early moments, before the [First Standard](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-262,%201st%20edition,%20June%201997.pdf) was really made, and where as you remember is **4.2.1 Objects**:

> ECMAScript supports prototype-based inheritance. Every constructor has an associated prototype, and **every object created** **by** that constructor has **an** **implicit** **reference** to the prototype (called the object’s prototype) associated with its constructor. Furthermore, a prototype may have a non-null implicit reference to its prototype, **and** so on; **this is called the** **prototype chain**.

Wow… And if you, as me, indeed think this is one of the most important [CS](https://en.wikipedia.org/wiki/Computer_science) inventions, then how would you explain that effect it made on you, and all the possibilities your imagination produced when you were reading it?

Let’s get back again to the beginning. **_1995 is here_**. You are Brendan Eich, and you [have to invent](https://brendaneich.com/2017/12/my-dotjs-2017-keynote/) new programming language. Probably you like [Lisp](https://en.wikipedia.org/wiki/Lisp_%28programming_language%29) or [Scheme](https://en.wikipedia.org/wiki/Scheme_%28programming_language%29), at least in some parts. And there also is an [Inheritance Problem](https://en.wikipedia.org/wiki/Inheritance_%28object-oriented_programming%29) you have to solve somehow: cause there must be some sort of [OOP](https://en.wikipedia.org/wiki/Object-oriented_programming) in that new language. So _think_: you have to mix all the things you like and might be some things you don’t like, and make this coctail Good Enough for nobody will see the difference between, until the moment there is a real reason to look inside.

And now the question is again:

>**how will you go with Inheritance?**

Let now switch back to our regular life. What all we know about Inheritance? Some obvious parts of answers to this question:

1.  Most of all life is based on [Genome](https://en.wikipedia.org/wiki/Genome). It is a storage of data about probable creature properties and behaviour. Each one of us can infer it and own it’s part by being alive from previous life cycle generation.

2.  You can make creature using two techniques: combining two predecessors or by [monocous cloning](https://en.wikipedia.org/wiki/Monoicous) one of them. For sure, today you can mix some genome parts from more than two, but this is not so natural and obvious.

3.  Time matters. If some necessary properties are not yet invented or not exists anymore, you are unable to inherit them, you can only re-create them from scratch being genome designer. And also there is a Legacy of something you own from your predecessors not through genome but by law of property, and this might be important too.

Then, here we are now again, and the right question for our newly crafted language is: 

>**Inheritance of What we have to design?**

And, in any ways, we have to be able to fill the gaps between programming and life, while solving this Inheritance Problem, just because if then we will not be able to name this as an Inheritance at all.

And yet one moreover: we are in 1995, using very powerful PC with only 32Mb of memory, and we trying to implement Scripting Language, so we have to take care of this memory, we have to be able to use as small amount of it as it can be possible. Each piece of data, especially [Strings](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String), consume a lot of memory, and we have to be able to define that piece only once, and then make reference as much times as we need to have an access to our data through some techniques.

>**Now we can see how hard that question was.**

There is a popular opinion, that “_JavaScript made of_ [_Objects_](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object)_”_, so we can answer the question of what have to Inherit **_from_** and **_to_**: **Objects**. And thinking of on that memory economy we have to store our data in Objects, also, mixing their references to data between Inherited properties of that Objects. Now we can see **Why** being in 1995 **we** indeed **need** a design based on a prototype chain: it will help us to gain the memory economy as far as it is possible. And I think it is still the point that matters.

And here we can again rely on design. Based on the opinion “_everything is an Object”_ we might be able to Clone  something. And **_what is Cloning_**? As I think, describing our requirements we might mean something like Structure Clones, or [Shallow Copies](https://en.wikipedia.org/wiki/Object_copying#Shallow_copy), or some of modern [Object.assign](http://Object.assign%28%29%20-%20JavaScript%20|%20MDN%20https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Object/assign) ancestors. Back in 1995 we can use just structure copy, therefore we can use some of code that works with **`for (var i in ClonedObject){}`** concept for doing this, because [it was already invented](https://www.ecma-international.org/publications/files/ECMA-ST-ARCH/ECMA-262,%201st%20edition,%20June%201997.pdf#sec-12.6.3) for the first version of standard: as you can see, this might still be working as well

```javascript
	// back in 1995 cloning
	// it is not deep clone,
	// though we might not need deep at all
	var cloneProps = function (clonedObject, destinationObject) {
	  for (var key in clonedObject) {
	    destinationObject[key] = clonedObject[key];
	  }
	};
```


Also I’d recommend to take a peek [deep-extend](https://github.com/unclechu/node-deep-extend) for understanding of making clones with JavaScript instead of obvious **`for... in`** implementation. Then, let’s try to imagine how using this Cloning definition sequentially, will help us to reach the following explanations of cloning pattern seems to be working in the past old ancient times:

*   Object from Constructor **_cloning_**_:_ we will use Constructor for making at least two new different Clones: clone1.foo == clone2.foo

```javascript
	// cloneProps is described above
	var SomeConstructor = function (clonedObject) {
	  cloneProps(clonedObject, this);
	};
	var someExistingObjectToClone = {
	  foo : 'bar'
	};
	var clone1 = new SomeConstructor(someExistingObjectToClone);
	var clone2 = new SomeConstructor(someExistingObjectToClone);
```


*   Constructor from Constructor **_cloning_**_:_ we will use one Constructor for implementing behaviour of another one Constructor: AnotherConstructor makes the same as SomeConstructor, and we don’t use cloneProps

```javascript
	var SomeConstructor = function () {
	  this.a = 'cloned';
	};
	var AnotherConstructor = function () {
	  // Function.prototype.call
	  // was already invented in 1st ECMA-262
	  SomeConstructor.call(this);
	};
```


*   Constructor from Object **_cloning_**_:_ we will use Object for making at least two new Constructors with props cloned from that Object: calling SomeConstructor behaves the same as calling OtherConstructor

```javascript
	var existentObject = {
	  foo : 'bar'
	};
	var SomeConstructor = function () {
	  cloneProps(foo, this);
	};
	var OtherConstructor = function () {
	  cloneProps(foo, this);
	};
```

*   Object from Object **_cloning_**_:_ we will use Object for making at least few new different Cloned Objects. So it is just **`cloneProp(cloned, destination)`** example as it’s described above.

_As we can see, cloning is obvious, it is ok, it works fine, but…_

**How** well we will **make an Inheritance** it for **Instances** using **Combinations of Predecessors** technique?

*   **_Inherit_** Object from Constructor: as it is a Constructor Purpose itself, so this might be used as well: this is a common pattern, described everywhere

```javascript
	var existentObject = {
	  foo : 'bar'
	};
	var SomeConstructor = function () {};
	SomeConstructor.prototype = existentObject;

	var inheritedObject = new SomeConstructor();

	// we have no instanceof yet in ECMA 262 of 1995
	// therefore we are unable to rely on this
	window.alert(inheritedObject.foo); // bar
```


*   **_Inherit_** Constructor from Constructor. No doubt, the first who did this was genius. This is also classic example everybody knows. Here could be a much more “advanced” example, though nothing for

```javascript
	var FirstConstructor = function () {
	  this.foo = 'bar';
	};
	var InheritedConstructor = function () {
		FirstConstructor.call(this);
	};
	InheritedConstructor.prototype = {
	  bar : 'foo'
	};
	InheritedConstructor.prototype.constructor = FirstConstructor;
	var inherited = new InheritedConstructor(); // { foo : 'bar', bar : 'foo' }
```

*   **_Inherit_** Constructor from Object: you just rely on **`.prototype = object`** each time you make an Inheritance, therefore nothing to describe here additionally, it is always included, and any time you can change199x **`Constructor.prototype`** and it will Bubble through all of inherited Instances immediately, because memory is shared among them.


*   **_Inherit_** Object from Object: **that is what it is**, Again! You just put any **_Existing Object_** to **`Constructor.prototype`** and after making construction calling **`new Constructor`** you will get newly **_Inherited Instance_** of that **_Existing_** prececessor **_Object_**. And, you have Explicitly put Existing Object to **`Constructor.prototype`**, only then there will be implicit reference. And only then [**instanceof**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/instanceof), which was initially described almost four years after Prototype Chain aroused in JS, will rely on that Constructor.


But yet one thing from Standart: **_do this all as deep as it will be necessary_** ...

> **_... and so on ..._**

_for our inheritance_ [_Trie_](https://en.wikipedia.org/wiki/Trie)_’d prototype chain of 1995._

---

#### Let’s try make Instance **Inheritance really deep in1995**

Indeed, let assume we have two Instances **`{ objects }`**, not the Constructors, but just plain Objects. And we wish to inherit one from another, and probably from another, and another, as the Standard says **`and so on`**?

**But How?**

Let’s look further, deeper. The right question here is, again that we noticed before: **Inheritance of What we have to design?**

We don’t need that Instances itself. We need their **properties**: **_associated data_**, consuming memory; and also we need some **behaviour**: **_methods utilising that data_**. It would be [Fair](https://en.wikipedia.org/wiki/Laissez-faire) enough if there will also be some ability to check what from and where to we are going to Inherit. It would be also good if we can Re-Produce that design of Inheritance Pattern in future, meaning if and when we Inherit One from Another we will always get the same result, regarding to what we expect by description (contract). Though it might be also useful to fixate that creation moment somehow, cause, indeed, predecessors might change during time, and it would be not so nice we will change successor giving respect to that changes.

As all of our code is a combination of data and behaviour, would it be nice that we are mixing them together utilizing that Inheritance pattern?

As for me this all looks like what we see when we observe Life in all of it majestic forms. From the earlies One-Cell Creatures to their Multi-Cell Successor and then other Successors, then to the Animals… and then to [humans](https://en.wikipedia.org/wiki/Homo_sapiens) and [humanity](https://en.wikipedia.org/wiki/Humanity_%28virtue%29), [Tribes](https://en.wikipedia.org/wiki/Tribe), [Civilizations](https://en.wikipedia.org/wiki/Civilization) and to the [Intelligence](https://en.wikipedia.org/wiki/Intelligence), to [Space](https://en.wikipedia.org/wiki/Konstantin_Tsiolkovsky) and [AI](https://en.wikipedia.org/wiki/Artificial_intelligence) and going to the Galaxy, to Stars…

> _and:_ 
> **“ … All we need to do is make sure we keep talking … ”**

that incredibly mindful quote from [Stephen Hawking](https://en.wikipedia.org/wiki/Stephen_Hawking) which was then popularised by [Pink Floyd](https://en.wikipedia.org/wiki/Pink_Floyd)’s awesome [masterpiece](https://en.wikipedia.org/wiki/Keep_Talking).

And [Programming Languages](https://en.wikipedia.org/wiki/Programming_language), utilizing [Message Passing](https://en.wikipedia.org/wiki/Message_passing) and [Flow Based](https://en.wikipedia.org/wiki/Flow-based_programming) concepts are the Successors of that Idea. From just Raw Data we develop everything on the top of this ground level [API](https://en.wikipedia.org/wiki/Application_programming_interface). I think it is an [Art](https://en.wikipedia.org/wiki/Art) as it is, and we might see as it works for JavaScript as well, deeply nested in language structure: referencing data structures through prototype chain.

So, let suppose we have both Parents, they communicate (**_keep talking_**) through time, and then one moment they decide to combine their emotions and feelings together bringing a Child. And this Child then grown, meeting another grown Child, they communicate (**_keep talking_**) and deliver another child. And again and again and again, from the ancient times to exact this moment: this is the [Circle of Life](https://en.wikipedia.org/wiki/Circle_of_Life).

And as we can see, **_naturally_** we have to use **_Two Parents_**, no less or more, cause if we use one, it will be cloning, if we use more than two, it would be engineering: [Designed Genome](https://en.wikipedia.org/wiki/Gene_Designer) of the [DNA](https://en.wikipedia.org/wiki/DNA).

**_Two creatures, not Less or More._** And they combine their properties using Inheritance, and then their children become owners of their Legacy. And each moment they combine themselves, they give us new kid. It is so simple.

Sounds strange, though, yes, we have all the parts we have to have to craft Inheritance pattern in JavaScript starting from 1995. And the main part is that **4.2.1 Objects**, with it’s **implicit referencing** through the prototype.

And this just as it is, you **_combine Parent Object_** with **_ParentConstructor_** through it’s**_.prototype_** and **_then_** this **_Constructor_** will probably make you **_ChildObject_** when you say **_new_** keyword: this is so simple, so obvious, and so terrific

```javascript
	var ParentObject = {
	  foo : 'bar'
	};
	var ParentConstructor = function () {};
	ParentConstructor.prototype = ParentObject;

	var ChildObject = new ParentConstructor();

	// starting from 1995 and then ECMA 262
	// we are able to say new
	// each time we need a ChildObject 
```

Here we have both parents, and then the moment when we say **new** we ask them to communicate. If they don’t wish to communicate process will fail with an error, and Life (js [runtime](https://en.wikipedia.org/wiki/Run_time_%28program_lifecycle_phase%29) [compiler](https://en.wikipedia.org/wiki/Compiler)) will say you what went wrong.

And then, sure, we are asking about [Genetic Tree](https://en.wikipedia.org/wiki/Phylogenetic_tree) or, which might be much more simplier about some sort of [Genealogy](https://en.wikipedia.org/wiki/Genealogy). And the answer is the same, your **_Child Object_** is grown, and **_become Parent_** Object, then met another **_Constructor Object_** and **_when you say_ “new” ** —  awesome: 

```javascript
	// this Assignment is just to show it grew up
	var ChildObjectGrownToParent = ChildObject;

	var AnotherConstructor = function () {};
	AnotherConstructor.prototype = ChildObjectGrownToParent;

	var SequentialChildObject = new AnotherConstructor();
	// checking Life Cycle ;^)
	console.log(ChildObject instanceof ParentConstructor); // true
	console.log(SequentialChildObject instanceof ParentConstructor); // true
	console.log(SequentialChildObject instanceof AnotherConstructor); // true
```


If you combine both examples, you will see working result of Inheritance Genome. And you can continue doing this as far in deep as it would be necessary!

I indeed hope this was the main Idea when design of Prototype Chain was crafted, because, as all we know this way causes some neat problems…

---


**`1:` Community …** As you can easily check, **assignment** to**.prototype** of **_ParentConstructor_** or **_AnotherConstructor_** is a very strong S[ocial Contract](https://en.wikipedia.org/wiki/Social_contract) for our Tribes, it produces references from **_ParentObject_** props (`**.foo`** ) to the Successors: kids, **_ChildObject_** and **_SequentialChildObject_**. If you will change that assignment, ouch, this references will gone forever. If you will cheat and reassign this references, oops, our kids will Inherit another object props. So, when **_combining parents with_** an assignment to**_.prototype_**, probably we may tell we are going to create [Family](https://en.wikipedia.org/wiki/Family), because our parents might then produce a lot of children, and using “**new**” keyword we may ask them to deliver another one as much time as it would be necessary for our [Life Story](https://en.wikipedia.org/wiki/User_story). And then if we will destroy that.prototype based referencing we will destroy all of children properties they Inherited from the Family, such a crime drama. ;^)

Therefore this all is about Legacy and we have to take care of this, if we going to build [reliable](https://en.wikipedia.org/wiki/Software_quality) and [maintaineable](https://en.wikipedia.org/wiki/Maintainability) code. Sure respecting [S.O.L.I.D.](https://en.wikipedia.org/wiki/SOLID), [Liskov substitution Principle](https://en.wikipedia.org/wiki/Liskov_substitution_principle) with [Design by Contract](https://en.wikipedia.org/wiki/Design_by_contract), and then probably some of [GRASP](https://en.wikipedia.org/wiki/GRASP_%28object-oriented_design%29) was not that problem in 1995. But it is obvious all that methodologies was not made from scratch, they were born much earlier.

**`2:` Family …** As we can easily check, our **_ParentObject_** allowed to be very **_frivolous_** in combining itself with other Constructors. It is not fair, but we are able to use as much Constructors as we wish, Inheriting ParentObject for making other families of children. From the other side each **_Constructor_** is **_tightly combined_** with ParentObject by assignment to**_.prototype_**_._ When we wish no harm to children we should keep that reference as long and far in time as it is possible. We might name all this as tragedy and art of our Tribe [History](https://en.wikipedia.org/wiki/History). Though also, it will protect us from [Amnesia](https://en.wikipedia.org/wiki/Amnesia) of what we referenced **_from_** **_and to_**, and why our children have all this [Legacy](https://en.wikipedia.org/wiki/Legacy_code). Giving a respect to [Mnemosyne](https://en.wikipedia.org/wiki/Mnemosyne), it is realy easy to [test](https://en.wikipedia.org/wiki/Software_testing) our prototype chain [Trie](https://en.wikipedia.org/wiki/Trie) finding [Artifacts](https://en.wikipedia.org/wiki/Artifact_%28software_development%29) what we did wrong.

**`3:` [**Senescence**](https://en.wikipedia.org/wiki/Senescence) …** Our **_ParentObject_** and our **_Constructor_** could be somehow damaged in time of our Life (runtime) is doing what it was designed for. We might keep care of what we are doing, but nowone is protected from errors. And all that changes might bring some harm to our Inheritance Successors through that prototype chain. We should keep in mind about [Memory Leaks](https://en.wikipedia.org/wiki/Memory_leak). We might be able to destroy unnecessary parts of our code. We might be able to free the memory which is no more used for our [Life Cycle](https://en.wikipedia.org/wiki/Object_lifetime). Also we should get rid of ability to bring [Temporal Paradox](https://en.wikipedia.org/wiki/Temporal_paradox) to our prototype chains, though it is easy to reference Parent from Child, it might be very harmful, so we should not use that techniques of jumping from Future to Past. Finally it is possible to get full stack or pile of hardly reproducible [Heisenbugs](https://en.wikipedia.org/wiki/Heisenbug) if we will try to measure something that is possible to change during time.

---

### Chronicle of Solution

It is easy, obvious and very pleasant. Instead of thinking of our Constructor as Mommy and our ParentObject as Daddy let’s try to describe them in terms of [Egg-Cell](https://en.wikipedia.org/wiki/Egg_cell) and… ough… [Pollen](https://en.wikipedia.org/wiki/Pollen). So when we will make a [Zygote](https://en.wikipedia.org/wiki/Zygote) using “new” keyword, then, well, there is no harm to our Imagination.

Doing so, we will get rid of all that three problems. For sure then we need Egg-Cell Factory: Factory of Constructors. This might be each one of our Parents, might be Mother or Father, say as you wish, but the main point here is when we wish to say “new” we have to craft Egg-Cell and bring Pollen to it for growing up new [Galanthus flower](https://en.wikipedia.org/wiki/Galanthus) in such a far and still snowing and windy Spring of 2020:

```javascript
	var Pollen = { season : 'Spring' };
	// factory of constructors 
	var FlowersFactory = function (proto) {
	  var FlowerEggCell = function (sort) {
	    this.sort = sort;
	  };
	  FlowerEggCell.prototype = proto;
	  return FlowerEggCell;
	};
	var FlowerZygote = FlowersFactory(Pollen);
	var galanthus = new FlowerZygote('Galanthus');
```

That is it, now we see how it works. And don’t forget to check galanthus.season please!

For sure, [Cyclomatic Complexity](https://en.wikipedia.org/wiki/Cyclomatic_complexity) of solutions you will do utilizing this pattern is absolutely outstanding and as for me they can be compared with something you see solving [Zebra Puzzle](https://en.wikipedia.org/wiki/Zebra_Puzzle). Therefore I made a [**_library_**](https://www.npmjs.com/package/mnemonica), which might help with constructors [chaining](https://en.wikipedia.org/wiki/Method_chaining) and [memoization](https://en.wikipedia.org/wiki/Memoization).

I can’t prove it, but this technique is successfully used for two decades from time to time when you need to be sure you did the best with Inheritance. As you can check it is more than testable, reproducible and maintainable. Didn’t telling the whole story here, we just rely on fact: JavaScript designed _enough_ _good_ even for making Genealogy Trie with Inheritance. Also we didn’t discuss the [Class](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Classes) degradation, but you can easily implement **_FlowerEggCellClass_** instead of just **_FlowerEggCell_** inside of **_FlowersFactory_**. The main part here is as it is, if you will wish to use **_instanceof_** checking for your flowers you will see they all are made from that **_FlowerEggCell_** constructors you referenced through **_FlowerZygote_**. And, for sure, you can change **_FlowerZygote_** in time, it will bring no harm for **_FlowersFactory_**, it will continue be able to produce new “[referenced](https://en.wikipedia.org/wiki/Reference_design)” constructors in future according to the design you did.

My hope this article will reveal all uncertainty with how important **.prototype** keyword is, and then seeing usage of [**`null`**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/null) in place of [**`this`**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/this) for [**`.bind(null, ...`**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/bind) or [**`.call(null, ...`**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/call) or [**`.apply(null, ...`**](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_objects/Function/apply) you will feel [Sorrow](https://en.wikipedia.org/wiki/Sorrow_%28Pink_Floyd_song%29) about current [design state](https://en.wikipedia.org/wiki/Blueprint) of the code style they made.

Thank You for reading this!

All in good time!

Sincerely yours V

PS 1:
[RU version](https://habr.com/ru/post/470994/)

PS 2:
Exported from [Medium](https://medium.com) on February 25, 2020.
[Canonical link](https://medium.com/@went.out/javascript-prototype-inheritance-point-of-view-from-boring-nerd-9c7924afc9fc) on October 9, 2019.




