# Books

Here's a table of everyone's learning book organized by weekly progress.

{% githubapi %}
https://api.github.com/repos/bigdatahci2015/book/forks
{% endgithubapi %}

The lodash code below retrieves the name and the avatar url of each person in order to generate
the table.
{% lodash %}
return _.map(data, function (d) {
        return {
            name: d.owner.login,
            avatar: d.owner.avatar_url
        }
    })
{% endlodash %}

<table>
{% for d in result %}
<tr>
    <td>
        <img src="{{d.avatar}}" width="50"/>
    </td>
    <td>
        <a href="http://{{d.name}}.github.io/book">{{d.name}}</a>        
    </td>
    {% for week in [1,2] %}
    <td>
        <a href="http://{{d.name}}.github.io/book/learning/week{{week}}/">week {{week}}</a>
    </td>
    {% endfor %}
</tr>
{% endfor %}
</table>
