# replayable-web-quiz

*Introduction*

Ever wanted to do intense js knowledge training? There are few guides and few tests, but once you've done them, they are of no use, just because now you remember all answers, and test result will be not valid.

There are a plenty of js/web quizes and tests on the internet, but all of them have one problem: you can't redo them later to see how your expertise had grown. The project intends to make question generation automated.

So instead of specifying a one time use list of questions and aswers, we specify just choose:

1. What content areas should questions cover. Example: plain javascript, angular, html, css.
2. What features should questions cover. Example: javascript scopes, javascript comma operator, angular services, html flex, css specifity.
3. A degree of misleading. For example, how many false suggestions should be proposed.

Personally I dislike a misleading questions, because they test not skill but perception and attention, but some companies may employ such tests, so we need place to train them.

*Solution*

1. There so many technologies there, and one person can't know all of them. So question generators should be crowd-sourced. There, RWQ (replayable-web-quiz) should be a website which allows people add question generators, test them, rate them, and be rewarded with reputation which allows them make more useful things then before. But thats a big piece of work, for now we can just do some simple js tests to get question generation done.
2. So how we do question generation? It somewhat close to my other (private) project based on semantical ontonetwork, so I can use some ideas from there. Basically, there are entites which represent certain content features (for example, javascript function hoisting). Each such entity does have: code form, action and description. 
 1. Code form does represent a pattern of code, i.e. keywords, placeholders, structure. Basically, it's a grammar. We may use code form for autogeneration. Futher, we may use abovementioned private project for the code forming.
 2. Action is what the code do. Js is well known for it's resistance to code-analysis tools, so we dont try do it here. We can just evaluate code and see it's results. However we need to generate both right and wrong answers. To generate wrong answers, we may do small substitutions here and there in the tested code. I'm sure there is a better solution, but have't figured yet.
 3. Description is a human readable text which can use used in learning mode (a mode where code piece is throughtfully described).

