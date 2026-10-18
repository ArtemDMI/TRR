<div class="wtracker_default_mes_template">
    <!-- Main Scene Information -->
    <table>
        <tbody>
            <tr>
                <td>Time:</td>
                <td>{{data.time}}</td>
            </tr>
            <tr>
                <td>Location:</td>
                <td>{{data.location}}</td>
            </tr>
            <tr>
                <td>Weather:</td>
                <td>{{data.weather}}</td>
            </tr>
        </tbody>
    </table>

    <!-- Collapsible Detailed Tracker -->
    <details>
        <summary><span>Tracker Details</span></summary>
        <table>
            <tbody>
                <tr>
                    <td>Environment:</td>
                    <td>{{data.environment}}</td>
                </tr>
                <tr>
                    <td>Present:</td>
                    <td>
                        <!-- Joining an array of strings. Assumes a 'join' helper. -->
                        {{join data.charactersPresent ', '}}
                    </td>
                </tr>
            </tbody>
        </table>

        <!-- Character Details Section -->
        <div class="mes_wtracker_characters">
            <!-- Looping through the array of character objects -->
            {{#each data.characters as |character|}}
            <hr>
            <strong>{{character.name}}:</strong><br>
            <table>
                <tbody>
                    <tr>
                        <td>Position:</td>
                        <td>{{character.postureAndInteraction}}</td>
                    </tr>
                    <tr>
                        <td>Limited:</td>
                        <td>{{#each character.limited}}{{this}}{{#unless @last}}; {{/unless}}{{else}}Ограничения не установлены{{/each}}</td>
                    </tr>
                    <tr>
                        <td>NotKnow:</td>
                        <td>{{#each character.notKnow}}{{this}}{{#unless @last}}; {{/unless}}{{else}}Ключевые пробелы в знаниях не установлены{{/each}}</td>
                    </tr>
                </tbody>
            </table>
            {{/each}}
        </div>
    </details>
</div>
<hr>
