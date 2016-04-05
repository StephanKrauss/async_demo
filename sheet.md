## Funktionen der Javascript Bibliothek 'async.js'

### Funktionen zur Nutzung von Kollektionen

* [`each`](#each), `eachSeries`, `eachLimit`
	* Applies the function iteratee to each item in coll, in parallel  
* [`forEachOf`](#forEachOf), `forEachOfSeries`, `forEachOfLimit`
	* Like each, except that it passes the key (or index) as the second argument to the iteratee.
* [`map`](#map), `mapSeries`, `mapLimit`
	* Produces a new collection of values by mapping each value in coll through the iteratee function.
* [`filter`](#filter), `filterSeries`, `filterLimit`
	* Returns a new array of all the values in coll which pass an async truth test.
* [`reject`](#reject), `rejectSeries`, `rejectLimit`
	* The opposite of filter. Removes values that pass an async truth test.
* [`reduce`](#reduce)
	* Reduces coll into a single value using an async iteratee to return each successive step.
* [`reduceRight`](#reduceRight)
	* Same as reduce, only operates on coll in reverse order.
* [`detect`](#detect), `detectSeries`, `detectLimit`
	* Returns the first value in coll that passes an async truth test.
* [`sortBy`](#sortBy)
	* Sorts a list by the results of running each coll value through an async iteratee.
* [`some`](#some), `someLimit`, `someSeries`
	* Returns true if at least one element in the coll satisfies an async test.
* [`every`](#every), `everyLimit`, `everySeries`
	* Returns true if every element in coll satisfies an async test.
* [`concat`](#concat), `concatSeries`
	* Applies iteratee to each item in coll, concatenating the results.

### Kontrolle der Steuerung

* [`series`](#seriestasks-callback)
	* Run the functions in the tasks collection in series, each one running once the previous function has completed.
* [`parallel`](#parallel), `parallelLimit`
	* Run the tasks collection of functions in parallel, without waiting until the previous function has completed. 
* [`whilst`](#whilst)
	* Repeatedly call fn, while test returns true. 
* [`doWhilst`](#doWhilst)
	* The post-check version of whilst. To reflect the difference in the order of operations, the arguments test and fn are switched.
* [`until`](#until)
	* Repeatedly call fn until test returns true.
* [`doUntil`](#doUntil)
	* Like doWhilst, except the test is inverted.
* [`during`](#during)
	* Like whilst, except the test is an asynchronous function that is passed a callback in the form of function (err, truth)
* [`doDuring`](#doDuring)
	* The post-check version of during. 
* [`forever`](#forever)
	* Calls the asynchronous function fn with a callback parameter that allows it to call itself again, in series, indefinitely. 
* [`waterfall`](#waterfall)
	* Runs the tasks array of functions in series, each passing their results to the next in the array. 
* [`compose`](#compose)
	* Creates a function which is a composition of the passed asynchronous functions. 
* [`seq`](#seq)
	* Version of the compose function that is more natural to read. 
* [`applyEach`](#applyEach), `applyEachSeries`
	* Applies the provided arguments to each function in the array, calling callback after all functions have completed. 
* [`queue`](#queue)
	* Creates a queue object with the specified concurrency. 
*  [`priorityQueue`](#priorityQueue)
	* The same as queue only tasks are assigned a priority and completed in ascending priority order. 
* [`cargo`](#cargo)
	* Creates a cargo object with the specified payload.
* [`auto`](#auto)
	* Determines the best order for running the functions in tasks, based on their requirements.
* [`autoInject`](#autoInject)
	* A dependency-injected version of the auto function. 
* [`retry`](#retry)
	* Attempts to get a successful response from task no more than times times before returning an error. 
* [`retryable`](#retryable)
	* A close relative of retry. 
* [`iterator`](#iterator)
	* Creates an iterator function which calls the next function in the tasks 
* [`times`](#times), `timesSeries`, `timesLimit`
	* Calls the iteratee function n times, and accumulates results in the same manner you would use with map. 
* [`race`](#race)
	* Runs the tasks array of functions in parallel, without waiting until the previous function has completed. 

### Werkzeuge

* [`apply`](#apply)
	* Creates a continuation function with some arguments already applied. 
* [`nextTick`](#nextTick)
    * Calls callback on a later loop around the event loop. 
* [`memoize`](#memoize)
	* Caches the results of an async function. 
* [`unmemoize`](#unmemoize)
	* Undoes a memoized function, reverting it to the original, unmemoized form. 
* [`ensureAsync`](#ensureAsync)
	* Wrap an async function and ensure it calls its callback on a later tick of the event loop. 
* [`constant`](#constant)
	* Returns a function that when called, calls-back with the values provided. 
* [`asyncify`](#asyncify)
	* Take a sync function and make it async, passing its return value to a callback. 
* [`wrapSync`](#wrapSync)
* [`log`](#log)
	* Logs the result of an async function to the console.
* [`dir`](#dir)
	* Logs the result of an async function to the console using console.dir to display the properties of the resulting object. 
* [`noConflict`](#noConflict)
	* Changes the value of async back to its original value, returning a reference to the async object.
* [`timeout`](#timeout)
	* Sets a time limit on an asynchronous function.