# Snippets PHP/MySQL

## Mettre en majuscule des noms composés

```php
function ucname($string) {
	foreach (array('-', '\'') as $delimiter) {
		if ( strpos( $string, $delimiter ) !== false ) {
			$string = implode( $delimiter, array_map( 'ucfirst', explode( $delimiter, $string ) ) );
		}
	}
	return $string;
}
```

## Tronquer une chaîne sans couper un mot

```php
function get_excerpt($string, $nb_words = 22) {

	// wordwrap pour insertion de marqueurs ***
	$text = wordwrap( strip_tags( $string ), (int) $nb_words, "***", true );

 	// explode suivant les marqueurs ***
	$tcut = explode("***", $text);

	// la première partie du contenu à récupérer
	return $tcut[0];
}
```
