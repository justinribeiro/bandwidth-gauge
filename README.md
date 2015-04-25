# bandwidth-gauge

Polymer 0.8 element that shows an animated gauge based on data from a network adapter.

## Why?

Little something something to render data from [wan-snmp-to-firebase-bridge](https://github.com/justinribeiro/wan-snmp-to-firebase-bridge) for [GDG Oakdale's Firebase Code Day](http://www.meetup.com/GDG-Oakdale/events/220949519/).

## Demo

There is a live demo of the element in action: [Placeholder]()

## Dependencies

1. [Polymer 0.8](https://www.polymer-project.org/0.8/)

## Basic Usage

```
<bandwidth-gauge name="Out" scale="3"></bandwidth-gauge>

```
## Options

You'll need to define at least the scale attribute to handle the math for the animation (which presume MB/s)

Attribute     | Options     | Default       | Description
---           | ---         | ---           | ---
`name`        | *string*    | `Gage`        | Title of the element
`scale`       | *int*       | ``            | Scale for gauge (in MB/s)
`bandwidth`   | *object*    | ``            | Defines the overall speed

`bandwidth` expects an object defined as:
```
{
  'speed': 10.01,
  'unit': 'MB/s'  // can be KB/s, MB/s, GB/s
}
```

Bandwidth can be set via regular JavaScript or a data binding:

```
<bandwidth-gauge id="out" name="Out" scale="3"></bandwidth-gauge>

<script>
  // No more polymer-ready in 0.8
  // https://github.com/Polymer/polymer/issues/1381
  document.addEventListener('WebComponentsReady', function() {
    document.getElementById("out").bandwidth = {
      'speed': 100.01,
      'unit': 'KB/s'
    };
  });
</script>

```

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -m 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D

## History

For detailed changelog, check [Releases](https://github.com/justinribeiro/bandwidth-gauge/releases).

## License

[Apache 2 License](http://opensource.org/licenses/Apache-2.0)