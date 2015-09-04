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
var r;
var body = _.pluck(data.comments,"body")
 
 var python =_.filter(body,function(n){return _.contains(n,"Python")})
var py=_.forEach(python, function(n) {
n=_.trimLeft(n,"Name: ");
n= _.first(n.split('\n')) ;
console.log(n);
 r=_(r).concat(n);
} );
 
 
 

return r; 

{% endlodash %}

Their names are {{result}}.

## Are there more Javascript lovers or Java lovers?

var check;
{% lodash %}

var body = _.pluck(data.comments,"body")
 
 var Javascript =_.size(_.filter(body,function(n){return _.contains(n,"Javascript")}))
 var javascript =_.size(_.filter(body,function(n){return _.contains(n,"javascript")}))
 var Javascript_total=_.add(Javascript,javascript)
 var Java =_.size(_.filter(body,function(n){return _.contains(n,"Java")}))
 
 var language =[{'lang' : 'Java' ,'size' : Java},{'lang' : 'Javascript' ,'size' : Javascript_total}]
 check=_.pluck(_.sortBy(language,'size'),'lang');
return _.last(check)
{% endlodash %}

The answer is {{result}}





## Who like the same food as `kjblakemore`?

{% lodash %}
var r;
var body = _.pluck(data.comments,"body")
 
 var python =_.filter(body,function(n){return _.contains(n,"Karen")})
var py=_.forEach(python, function(n) {n= _.last(n.split('\n')) ;
console.log(n);
 r=n;
} );
 
 
 return (_.size(_.filter(body,function(n){return _.contains(n,r)})))+1

 

{% endlodash %}


Their names are {{result}}.
