/* How many albums does the artist Led Zepplin have? */
SELECT COUNT(Albumid) AS totalAlbums 
FROM albums
WHERE Artistid  = (SELECT Artistid FROM artists WHERE name = 'Led Zeppelin')

/* Create a list of album titles and the unit prices for the artist Audioslave */
SELECT n.Name, u.UnitPrice
FROM ((albums t INNER JOIN artists n
				ON t.Artistid = n.Artistid)
INNER JOIN tracks u ON t.Albumid = u.Albumid)
WHERE n.Name = 'Audioslave'

/* Find the first and last name of any customer who does not have 
an invoice. Are they any customers returned from the query? */ 
SELECT n.FirstName, n.LastName, i.Invoiceid
FROM customers n 
	LEFT JOIN invoices i ON n.Customerid = i.Customerid
WHERE InvoiceId IS NULL

/* Find the total price of each album. What is the total price for
the album Big Ones? */
SELECT t.Title, SUM(p.UnitPrice)
FROM albums t
	INNER JOIN tracks p ON t.Albumid = p.Albumid
WHERE t.Title = 'Big Ones'
GROUP BY t.Title

/* How many records are created when you apply a Cartesian 
join to the invoice and invoice items table? */
SELECT a.InvoiceId D FROM invoices a CROSS JOIN invoice_items b;
