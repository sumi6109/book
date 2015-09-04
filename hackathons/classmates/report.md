{% import './data.html' as data %}

# Report

As a class, we brainstormed and came up with a long list of further questions we can ask based
on the "self-introduction" data. Out of these questions, our team chose to tackle on
the following:

# who submitted by the deadline


{% lodash %}
var body = _.pluck(data.comments,"body")
 
 var food =_.size(_.filter(body,function(n){return _.contains(n,"Sushi")}))
return "[answer]"
{% endlodash %}

# who has the github avatar


{% lodash %}
return "[answer]"
{% endlodash %}

# what percentage of people from computer science major

{% lodash %}
var body = _.pluck(data.comments,"body")
 
 var food =_.size(_.filter(body,function(n){return _.contains(n,"Computer")||_.contains(n,"CS")||_.contains(n,"cs\r")}))
return food
{% endlodash %}

the result is {{result}}
# How many ppl submitted on and befor the deadline 8/24/15

{% lodash %}

return _.size(_.pluck(_.filter(data.comments,function(chr){
                            return chr.created_at.split('T')[0].split('-')[2] <=24;}),"body"))

{% endlodash %}
the result is {{result}}
# who has same last name

{% lodash %}
return "[answer]"
{% endlodash %}
