{% data src="fcq.clean.json" %}
{% enddata %}

# Report

As a class, we brainstormed and came up with a long list of further questions we
can ask based on the FCQ data. Out of these questions, our team chose to tackle on
the following questions. Each member on our team is reponsible for one question.

# (Question 1) by (Name)

{% lodash %}
return "[answer]"
{% endlodash %}


# How many instructors have taught each subject?
 by (KariSantos)

{% lodash %}

var groups =_.groupBy(data,function(d){return d.Subject})
var result =_.mapValues(groups,function(t){ 
var pluckinst=_.pluck(t,'Instructors')
return _.size(_.uniq(_.flatten( _.map(pluckinst,function(t){return _.pluck(t,'name')}))))


})
return result

{% endlodash %}
{{result|json}}


<table>
{% for key, value in result %}
    <tr>
        <td>{{key}}</td>
        <td>{{value}}</td>
    </tr>
{% endfor %}
</table>


# (Question 3) by (Name)

{% lodash %}
return "[answer]"
{% endlodash %}

# (Question 4) by (Name)

{% lodash %}
return "[answer]"
{% endlodash %}

# (Question 5) by (Name)

{% lodash %}
return "[answer]"
{% endlodash %}
