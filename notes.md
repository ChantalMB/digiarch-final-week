# Week 12 & 13: Notes

- Rmd Project
  - Want to finish this --> feels like a good way to "wrap things up"
    - Goal: See what we can learn from the graves about aesthetics of each time period we have,
      - Sub goal: I wonder if location of cemeteries and conditions of the grave will hold any relevance?
  - Back to map
    - Just noticed this block of code in geojson that I think might be messing with things:
      ```
      {
       "type": "FeatureCollection",
       "features": [
      {
        "type": "Feature",
        "geometry": {
           "type": "Point",
           "coordinates":  { }
        },
        "properties": {
        "Label":"Burial.Ground.Name",
        "FIELD4":"Condition.of.monument",
        "FIELD5":"Condition.of.inscription",
        "FIELD6":"Monument.type",
        "FIELD7":"Letter.styles",
        "FIELD8":"Date.of.monument"
        }
      }
      ```
    - Start by running it with this block removed
      - Hm nothing changed EXCEPT no weird starting point from previous unrelated work like last time
    - Time to start from scratch
      - Ran original code and now it's serving my previous unsuccessful attempt??? --> is the previous process not being killed when I `ctrl+c`?
      - 304 code --> nothing is changing from previous instance...
      - Oh my god Chrome cached it
    - I have to clear the cache everytime I want to load my map...
      - Caching is disable for this page and yet here we are, switching to safari
    - Manually typing out the geojson points in another file seems to make the points show up --> something wrong with the file?
      - Going to reconvert and see what happens... --> nothing changed oh
      - Absolutely bizarre --> files share an identical format yet one compiles and the other refuses/throws 404 error
    - AH-HA! Breaks if there's any points that are missing coordinates --> going to clear the data of these via regex
      - Okay so some locations without coordinates had very valuable data --> inputted coordinates of cemetery so they could be included
    - Still breaking --> I think it's trying to parse the backslashes people used to devide up inscriptions
    - After cleaning the data and making it as plain as possible, it still will not load
      - Can get up to 15 points loaded when manually typed out...
      - Hm multiple graves in one cemetery seems to pose a problem
        - Because of zoomed out scale to encompass all cemeteries featured, each cemetery looks like it only has one marker
        - Changing colours doesn't help because of overlap --> would also interfere with how I want to represent different aspects of the data
  - Anddd now I've spent too much time fiddling with this map and don't have time to complete this activity entirely
    - One day I shall conquer Leaflet but for now... I accept my defeat
- AR
  - Isolating a single grave feels strange
    - Nice to preserve the family's post-mortem "togetherness" rather than having to separate them like into individuals like [we did when recording](https://hist-digitized.netlify.app/post/2020-10-04-week-3/)
  - Modelling getting a bit better --> closer to actual shape
    - Can reference my notes for scale
    - I cannot figure out for the life of me how to make the top of this monument pointy
