Configuration
=============

Custom Model
------------

Configure your [custom model](custom-model.md) :

### Model configuration

```yaml
meup_geolocation:
    address:
        entity_class: Acme\Bundle\AcmeBundle\Model\Address
    coordinates:
        entity_class: Acme\Bundle\AcmeBundle\Model\Coordinates
```

### Factories configuration

```yaml
    address:
        factory_class: Acme\Bundle\AcmeBundle\Factory\AddressFactory
    coordinates:
        factory_class: Acme\Bundle\AcmeBundle\Factory\CoordinatesFactory
```

Custom Hydrator
---------------



Configuration reference
-----------------------

you can configure your `app/config/config.yml` with the following

```yaml
meup_geolocation:
    address:
        entity_class:       Meup\Bundle\GeoLocationBundle\Model\Address
        factory_class:      Meup\Bundle\GeoLocationBundle\Factory\AddressFactory
    coordinates:
        entity_class:       Meup\Bundle\GeoLocationBundle\Model\Coordinates
        factory_class:      Meup\Bundle\GeoLocationBundle\Factory\CoordinatesFactory
    providers:
        google:
            api_key:        %geolocation_google_api_key%
            api_endpoint:   https://maps.googleapis.com/maps/api/geocode/json
            locator_class:  Meup\Bundle\GeoLocationBundle\Provider\Google\Locator
            hydrator_class: Meup\Bundle\GeoLocationBundle\Provider\Google\Hydrator
        bing:
            api_key:        %geolocation_bing_api_key%
            api_endpoint:   http://dev.virtualearth.net/REST/v1/Locations/
            locator_class:  Meup\Bundle\GeoLocationBundle\Provider\Bing\Locator
            hydrator_class: Meup\Bundle\GeoLocationBundle\Provider\Bing\Hydrator
```

The `app/config/parameters.yml` will contains your API keys :

```yaml
parameters:
    # ...
    geolocation_google_api_key: your_google_api_key
    geolocation_bing_api_key:   your_bing_api_key
```