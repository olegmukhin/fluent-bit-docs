# Slack

The Slack output plugin delivers records or messages to your preferred Slack channel. It formats the outgoing content in JSON format for readability.

This connector uses the Slack _Incoming Webhooks_ feature to post messages to Slack channels. Using this plugin in conjunction with the Stream Processor is a good combination for alerting.

## Slack Webhook

Before configuring this plugin, make sure to set up your Incoming Webhook. For detailed step-by-step instructions, review the following official documentation:

* [https://api.slack.com/messaging/webhooks\#getting\_started](https://api.slack.com/messaging/webhooks#getting_started)

Once you have obtained the Webhook address you can place it in the configuration below.

## Configuration Parameters

| Key     | Description                                                                                                          | Default |
|:--------|:---------------------------------------------------------------------------------------------------------------------|:--------|
| webhook | Absolute address of the Webhook provided by Slack                                                                    |         |
| workers | The number of [workers](../../administration/multithreading.md#outputs) to perform flush operations for this output. | `0`     |

### Configuration File

Get started quickly with this configuration file:

{% tabs %}
{% tab title="fluent-bit.yaml" %}

```yaml
pipeline:

  outputs:
    - name: slack
      match: '*'
      webhook: https://hooks.slack.com/services/T00000000/B00000000/XXXXXXXXXXXXXXXXXXXXXXXX
```

{% endtab %}
{% tab title="fluent-bit.conf" %}

```text
[OUTPUT]
    name                 slack
    match                *
    webhook              https://hooks.slack.com/services/T00000000/B00000000/XXXXXXXXXXXXXXXXXXXXXXXX
```

{% endtab %}
{% endtabs %}