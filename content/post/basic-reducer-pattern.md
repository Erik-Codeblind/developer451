---
title: "Basic Reducer Pattern"
date: 2020-12-16T16:59:32-05:00
summary: "A basic, framework agnostic, description of the concept behind the reducer pattern."
tags: ["React", "JavaScript", "Redux", "Reducer"]
---

The basic concept of a reducer is to provide a pure function defining the `types` of operations you're planning to perform on the values of the current `state`. 

A reducer performs one of a collection of `action`s using the values found in the current `state`, then outputs the `next` shape of state with those actions applied, as in `(state, action) => next`. The reducer does not actually update or alter the `state` itself, which is treated as an immutable moment in the application history. The expectation is that some other mechanism keeps track of the current `state` of the application from one moment to the next, typically in a `store`. 


{{< highlight javascript>}}
const count = 12;

const reducer = (state, action = { type: null, payload: null }) => {
  switch(action.type) {
    case 'INCREASE':
      return state + action.payload;
    case 'DECREASE':
      return state - action.payload;
    case 'MULTIPLY': 
      return state * action.payload;
    case 'DIVIDE':
      return state / action.payload;
    default:
      return state;
  }
};

console.log(reducer(count, {type: 'INCREASE', payload: 3 })) // 15
console.log(reducer(count, {type: 'DECREASE', payload: 2 })) // 10
console.log(reducer(count, {type: 'DIVIDE', payload: 3 })) // 4
console.log(reducer(count, {type: 'MULTIPLY', payload: 12 })) // 144
console.log(count); // 12 (count remains unchanged)
{{</ highlight>}}

{{<replit src="https://repl.it/@Erik_Codeblind/ReducerPattern">}}
