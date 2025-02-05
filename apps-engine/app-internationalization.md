# App Internationalization

One of the things you may have noticed when typing the slash command in the message composer box is that a weird description shows up. That's because we didn't create the localization file with proper entries for our slash command.&#x20;

Here's what you need to do:&#x20;

* Create a folder named `i18n` at the root and create a `json` file with the abbreviation of the language. For example, `en.json`, `pt.json`.
* You will be provided with all the keys of the app, and you just have to provide the corresponding text in the chosen language against each key. So in the UI, you can see the translated text.&#x20;
* Once you have included English values for the i18n variables we specified on the slash command class, you can see it in the UI.&#x20;
* For example, `submit.send` is a key for sending a message to the channel. This is how it will look like:&#x20;

{% code title="i18n/en.json" %}
```json
English
{
    "Submit.send": "Send Message to Channel"
}
```
{% endcode %}

{% code title="i18n/pt.json" %}
```json
{
    "Submit.send": "Enviar Mensagem para o Canal"
}
```
{% endcode %}

You need to create a separate `json` file for each language you want your app to support. These files should be organized under the `i18n` folder. You can call the same file to translate the content across several app interactions. Similarly, you can also define the values for other functions. For example, the `i18n` folder of the [Jitsi app](https://github.com/RocketChat/Apps.Jitsi/tree/master/i18n) contains the values for the supported languages.
