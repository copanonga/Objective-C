# Snippets para Objective-C

## Índice de contenidos

- [Refrescar celda](#refrescar-celda)
- [Imagen en escala de grises](#imagen-en-escala-de-grises)
- [NSSortDescriptor ordenar con número un string](#NSSortDescriptor-ordenar-con-número-un-string)


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
## NSSortDescriptor ordenar con número un string

```
NSArray *sortedArray;
sortedArray = [listado sortedArrayUsingComparator:(NSComparator)^(id a, id b) {
Modelo *modelo1 = a;
Modelo *modelo2 = b;
NSNumber *num1 = [NSNumber numberWithInt:[modelo1.stringAComparar intValue]];
NSNumber *num2 = [NSNumber numberWithInt:[modelo2.stringAComparar intValue]];

return [num2 compare:num1];
}];
listado = [sortedArray mutableCopy];
```
