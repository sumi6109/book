# Analysis

{% import './data.html' as data %}

After completing the warmup exercises, your task is to do four more slightly
more challenges analyses.

## How many students like sushi as their favorite food?

{% lodash %}


var body = _.pluck(data.comments,"body")
 
 var food =_.size(_.filter(body,function(n){return _.contains(n,"Sushi")}))
 

return food


 

{% endlodash %}

The answer is {{result}}.

## Who are the students liking Python the most?

{% lodash %}

var body = _.pluck(data.comments,"body")
 
 var python =_.filter(body,function(n){return _.contains(n,"Python")})
 
 

return _.size(python)

{% endlodash %}

Their names are {{result}}.

## Are there more Javascript lovers or Java lovers?

{% lodash %}
return "[answer]"
{% endlodash %}

The answer is {{result}}.

## Who like the same food as `kjblakemore`?

{% lodash %}
return "[answer]"
{% endlodash %}

Their names are {{result}}.
