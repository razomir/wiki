# Search in Log Files

#### Display all MAC Adresses, when the Delimiter is ':'

	grep -i '..:..:..:..:..:..' * | cut -d ':' -f 3-8 | sort

In this example 3 is the field, where the mac adress is located. From this point you have to add 5 as the '.' count as delimiter.

#### Get the last 100 Lines of a Log File

	tail -f -n 100 /var/log/php/error.log
