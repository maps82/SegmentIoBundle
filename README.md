# Segment Io Bundle
Bundle include segment.io library for analytics

include segmentio/analytics-php

Documentation
-------------

The bulk of the documentation is stored in the [Resources/doc](Resources/doc) folder in this bundle

## Installation

Installing the bundle via packagist is the quickest and simplest method of installing the bundle. Here are the steps:

### Step 1: Composer require

    $ php composer.phar require "farmatholin/segment-io-bundle":"dev-master"

### Step 2: Enable the bundle in the kernel

    <?php
    // app/AppKernel.php

    public function registerBundles()
    {
        $bundles = array(
            // ...
            new Farmatholin\SegmentIoBundle\SegmentIoBundle(),
            // ...
        );
    }

That's it! You are ready to use Segment.io with symfony2.

## Configuration
Required  segment write key:
```yml
# SegmentIoBundle Configuration
# app/config/config.yml
        segment_io:
            write_key: "%your_key%" #add your key
            env: prod #default prod. Can be prod (sending to segment) and dev (not sending)
            options:
                consumer: socket #default
                debug: false #default
                ssl: false #default
                max_queue_size: 10000 #default
                batch_size: 100 #default
                timeout: 0.5 #default
                filename: null #default
```

## Usage
Get `segment_io.analytics` service from the service container and start using it:

```php
$analytics = $this->get('segment_io.analytics');
$analytics->page()
```

Refer to [Segment.io analytics-php library](https://github.com/segmentio/analytics-php).