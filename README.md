# Wordpress
This is used for optimize speed of wordpress

# function.php (*********    Defer jQuery    *********)


// Defer Javascripts
// Defer jQuery Parsing using the HTML5 defer property
if (!(is_admin() )) {
function defer_parsing_of_js ( $url ) {
if ( FALSE === strpos( $url, '.js' ) ) return $url;
if ( strpos( $url, 'jquery.js' ) ) return $url;
// return "$url' defer ";
return "$url' defer onload='";
}
add_filter( 'clean_url', 'defer_parsing_of_js', 11, 1 );
}
