# Snippets para Objective-C

## Índice de contenidos

- [Refrescar celda](#refrescar-celda)
- [Imagen en escala de grises](#imagen-en-escala-de-grises)

## Refrescar celda

```
[tableView reloadRowsAtIndexPaths:[NSArray arrayWithObjects:indexPath, nil]withRowAnimation:UITableViewRowAnimationNone];
```

## Imagen en escala de grises

```
- (UIImage *)grayscaleImage:(UIImage *)image {

	CIImage *ciImage = [[CIImage alloc] initWithImage:image];
	CIImage *grayscale = [ciImage imageByApplyingFilter:@"CIColorControls"
									withInputParameters: @{kCIInputSaturationKey : @0.0}];
	return [UIImage imageWithCIImage:grayscale];

}
```
