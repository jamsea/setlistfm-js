[![Build Status](https://travis-ci.org/terhuerne/setlistfm-js.svg?branch=master)](https://travis-ci.org/terhuerne/setlistfm-js)

# setlist.fm API Wrapper for Node.js

This is an easy implementation of the setlist.fm API for Node.js. To start right away enter the following lines to your command line:

```
npm install setlistfm-js --save
```

This wrapper covers the brand new API of setlist.fm. To use the API, you need an API key of setlist.fm. You can apply for an API key here: [https://www.setlist.fm/settings/api]() (Please note that you need an setlist.fm account to procede)

## Function Reference
One quick information before we start: The whole wrapper is written for a Promise based implementation. And another thing: The whole documentation for the API can be found here, so if you have any questions about allowed search parameters this is your destination:
[https://api.setlist.fm/docs/1.0/index.html#resources]()

Okay, enough said - let's code!

### Setup
```javascript
var setlistfmClient = new setlistfm({
	key: "", // Insert your personal key here
	format: "json", // "json" or "xml", defaults to "json"
	language: "de", // defaults to "en"
});
```

### Get Artist Profile
```javascript
setlistfmClient.getArtist("8538e728-ca0b-4321-b7e5-cff6565dd4c0")
	.then(function(artist) {
		// Returns the artist profile of Depeche Mode
	})
	.catch(function(error) {
		// Returns error
	});
```

### Get Setlists of Artist
```javascript
setlistfmClient.getArtistSetlists("8538e728-ca0b-4321-b7e5-cff6565dd4c0", {
	p: 1
})
	.then(function(setlists) {
		// Returns page one of all Depeche Mode setlists
	})
	.catch(function(error) {
		// Returns error
	});
```

### Get City
```javascript
setlistfmClient.getCity("2921466")
	.then(function(city) {
		// Returns city profile
	})
	.catch(function(error) {
		// Returns error
	});
```

### Search for Artists
```javascript
setlistfmClient.searchArtists({
	artistName: "Linkin Park"
})
	.then(function(results) {
		// Returns results of the search
	})
	.catch(function(error) {
		// Returns error
	});
```

### Search for Cities
```javascript
setlistfmClient.searchCities({
	name: "New York"
})
	.then(function(results) {
		// Returns results of the search
	})
	.catch(function(error) {
		// Returns error
	});
```

### Search Countries
```javascript
setlistfmClient.searchCountries()
	.then(function(results) {
		// Returns a list of available countries
	})
	.catch(function(error) {
		// Returns error
	});
```

### Search for Setlists
```javascript
setlistfmClient.searchCountries({
	artistName: "Linkin Park"
})
	.then(function(results) {
		// Returns matching setlists of Linkin Park
	})
	.catch(function(error) {
		// Returns error
	});
```

### Search for Venues
```javascript
setlistfmClient.searchVenues({
	name: "Gruenspan"
})
	.then(function(results) {
		// Returns results of the search
	})
	.catch(function(error) {
		// Returns error
	});
```

### Get Setlist by specific Version
```javascript
setlistfmClient.getSetlistByVersion("43596f23")
	.then(function(setlist) {
		// Returns version of setlist
	})
	.catch(function(error) {
		// Returns error
	});
```

### Get Setlist
```javascript
setlistfmClient.getSetlist("53e493bd")
	.then(function(setlist) {
		// Returns setlist
	})
	.catch(function(error) {
		// Returns error
	});
```

### Get User
```javascript
setlistfmClient.getUser("terhuerne")
	.then(function(user) {
		// Returns my own setlist.fm profile ;)
	})
	.catch(function(error) {
		// Returns error
	});
```

### Get Concerts a User has attended to
```javascript
setlistfmClient.getUserAttended("terhuerne", {
	p: 1
})
	.then(function(setlists) {
		// Returns setlists of concerts that I have attended to
	})
	.catch(function(error) {
		// Returns error
	});
```

### Get Setlists a User has edited
```javascript
setlistfmClient.getUserEdited("terhuerne", {
	p: 1
})
	.then(function(setlists) {
		// Returns setlists that a user has edited	})
	.catch(function(error) {
		// Returns error
	});
```

### Get Venue
```javascript
setlistfmClient.getVenue("4bd78fbe")
	.then(function(venue) {
		// Returns venue
	})
	.catch(function(error) {
		// Returns error
	});
```

### Get Setlists of a Venue
```javascript
setlistfmClient.getVenueSetlists("4bd78fbe", {
	p: 1
})
	.then(function(setlists) {
		// Returns setlists of concerts that have happened at the given venue
	})
	.catch(function(error) {
		// Returns error
	});
```
