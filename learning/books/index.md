# Books

Here's a table of everyone's learning book organized by weekly progress.

{% data src="./forks.json" %}
{% enddata %}

The lodash code below retrieves the name and the avatar url of each person in order to generate
the table.
{% lodash %}
return _.sortBy(_.map(data, function (d) {
        return {
            name: d.owner.login,
            avatar: d.owner.avatar_url,
            url: d.owner.html_url
        }
    }), function(d) { return d['name'].toLowerCase()})
{% endlodash %}

<table>
{% for d in result %}
<tr>
    <td>
        <img src="{{d.avatar}}" width="50"/>
    </td>
    <td>
        <a href="{{d.url}}">{{d.name}}</a>        
    </td>
    {% for week in [1,2,3,4,5,6] %}
    <td>
        <a href="http://{{d.name}}.github.io/book/learning/week{{week}}/">W{{week}}</a>
    </td>
    {% endfor %}
    {% for week in [7,8] %}
    <td>
        <a href="http://{{d.name}}.github.io/book2/learning/week{{week}}/">W{{week}}</a>
    </td>
    {% endfor %}    
    {% for week in [9,10] %}
    <td>
        <a href="http://{{d.name}}.github.io/book3/week{{week}}/">W{{week}}</a>
    </td>
    {% endfor %}        
</tr>
{% endfor %}
</table>
