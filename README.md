# Snippets para Objective-C

## Índice de contenidos

- [Refrescar celda](#refrescar-celda)
- [Imagen en escala de grises](#imagen-en-escala-de-grises)
- [NSSortDescriptor ordenar con número un string](#NSSortDescriptor-ordenar-con-número-un-string)
- [UIAlertController: style action sheet](#UIAlertController:-style-action-sheet)


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

## UIAlertController: style action sheet

```
UIAlertController *alertController = [UIAlertController
											  alertControllerWithTitle:nil
											  message:nil
											  preferredStyle:UIAlertControllerStyleActionSheet];
		
		UIAlertAction *cancelar = [UIAlertAction
									   actionWithTitle:NSLocalizedString(@"Cancelar", nil)
									   style:UIAlertActionStyleCancel
									   handler:^(UIAlertAction *action)
									   {
										   NSLog(@"Cancel action");
									   }];
		
		UIAlertAction *accion = [UIAlertAction
								 actionWithTitle:NSLocalizedString(@"Acción", nil)
								 style:UIAlertActionStyleDefault
								 handler:^(UIAlertAction *action)
								 {
									
								 }];
		
		NSMutableAttributedString *textoTitulo = [[NSMutableAttributedString alloc] initWithString:NSLocalizedString(@"Título...", nil)];
		[textoTitulo addAttribute:NSFontAttributeName
					  value:[UIFont fontWithName:NSLocalizedString(@"tipoLetra", nil) size:19.0]
					  range:NSMakeRange(0, textoTitulo.length)];
		[alertController setValue:textoTitulo forKey:@"attributedTitle"];
		
		[alertController addAction:cancelar];
		[alertController accion];
		
		[self presentViewController:alertController animated:YES completion:nil];
```

