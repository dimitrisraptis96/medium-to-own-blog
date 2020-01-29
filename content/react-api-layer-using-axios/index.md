---
title: "React api layer using axios"
description: "I was searching the web like a maniac to organize my api calls to a decoupled from react components layer and I found no luck."
date: "2020-01-29T12:36:22.498Z"
categories: []
published: false
---

I was searching the web like a maniac to organize my api calls to a decoupled from react components layer and I found no luck. 

My main problem was that every API call needed to call this.setState react funtion in order to update the state

  

My solution

create a api folder with config file, a urls file and post, get, delete etc function generators that return the response data as promises and a data manipulation layer in order to polish and decorate the fetched data. 

const url =ENDPOINTS.url1

foo = (url ) => (axios.get(url).then(response => response.data)

//pass data to a decorator

.then(data => decorator(data)

### Inside react component 

the call would look like this one: 

import {getGenerator} from ‘api’;

import{dummyDecorator} from ‘dataDecorators’

getGenerator(url).then(data => decorator(data)).then(props => this.setState({…props}) )
