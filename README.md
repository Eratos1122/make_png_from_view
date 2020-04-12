# Make png from view

Swift:
--------------
```swift
func makePNGFromView(view: NSView) {
    var rep = view.bitmapImageRepForCachingDisplayInRect(view.bounds)!
    view.cacheDisplayInRect(view.bounds, toBitmapImageRep: rep)
    if let data = rep.representationUsingType(NSBitmapImageFileType.NSPNGFileType, properties: [:]) {
        data.writeToFile("/xxx/image.png", atomically: false)
    }
}
```
