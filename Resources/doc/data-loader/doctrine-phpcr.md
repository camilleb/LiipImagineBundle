# DoctrinePHPCRLoader

Load images from PHPCR ODM

This loader works the same as the GridFS loader with some minor changes in the
service definition:

``` xml
<service id="liip_imagine.data.loader.phpcr" class="Liip\ImagineBundle\Imagine\Data\Loader\DoctrinePHPCRLoader">
    <tag name="liip_imagine.data.loader" loader="doctrine_phpcr" />
    <argument type="service" id="liip_imagine" />
    <argument>%liip_imagine.formats%</argument>
    <argument>%symfony_cmf_create.static_basepath%</argument>
    <argument type="service" id="doctrine_phpcr.odm.document_manager" />
    <argument>%symfony_cmf_create.image.model_class%</argument>
</service>
```

Note there is an AbstractDoctrineLoader. It is quite easy to extend this abstract class
to create a new Doctrine loader for the ORM or another ODM.

- [Back to data loaders](../data-loaders.md)
- [Back to the index](../index.md)
