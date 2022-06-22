### Media

Media exists as an aspect of Object records. As such, media is not queryable on its own and can only be retrieved as part of an object.

The best way to find records with media is to include the `hasMedia: true` flag to your query, for example:
```
{
  object(hasImages:true) {
    id    
    multimedia
  }
}
```

#### Media Artifacts
These are the fields within the `multimedia` block. Each entry will contain several sizes of media, referred to as 'artifacts'. 
The current artifacts are:
  - `preview`: 350px on its shortest side.
  - `large`: 1024px on its shortest side.
  - `zoom`: A zoomable pyramid tiff generated from the source image. Only generated for media whose original is at least 300px on its shortest side.
  - `original`: The original image asset, published where the object is licensed as CC0.

The generated artifacts are stored in Amazon S3, and can be found at the `url` for the respective artifact block. For example: `multimedia.preview.url`




