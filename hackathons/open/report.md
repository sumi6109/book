# Report


Use only Javascript and SVG to produce a data analysis / visualization report.
{% data src="../fcq/fcq.clean.json" %}{% enddata %}
# Authors

This report is prepared by
* [Full name](link to github account)
* [Full name](link to github account)
* [Full name](link to github account)

<a name="top"/>
<div id="autonav"></div>

# (Question 1)


{% viz %}

{% title %}


What is distribution of Number of Hrs worked of department ?
{% solution %}

var grps= _.groupBy(data,'CrsPBADept')

 var values =_.mapValues(grps,function(d){
 hrs= _.pluck(d,'Workload')
 
  var hrs_string=_.map(hrs,function(d){return d.Hrs_Wk})
  var total_hrs=_.map(hrs_string,function(d){ return d.split('-')[1]})
  return _.sum(total_hrs)
 })
 
 console.log(values)
var data1=_.map(values,function(group,name){return { course_name:name ,hrswork:group}})
var max= _.max(_.pluck(data1,'hrswork'))
//console.log(data1)


function computeX(d, i) {
    return i * 20
}

function computeHeight(d, i) {
      return d.hrswork
}

function computeY(d, i) {
    return max
}

function computeColor(d, i) {
    return 'red'
}

var viz = _.map(data, function(d, i){
            return {
                x: computeX(d, i),
                y: computeY(d, i),
                height: computeHeight(d, i),
                color: computeColor(d, i)
            }
         })
console.log(viz)

var result = _.map(viz, function(d){
         // invoke the compiled template function on each viz data
         return template({d: d})
     })
return result.join('\n')

{% template %}

<rect y="${d.x}" height="{d.height}" width="20" style="fill:red;"/>


{% endviz %}



# (Question 2)

Use the warmup exercise as the template to produce an answer here.

# (Question 3)

Use the warmup exercise as the template to produce an answer here. Remove this
question if you work as a unit of two.
