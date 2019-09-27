# mysql
Borrar duplicados dentro de la misma tabla

UPDATE License as lic INNER JOIN License as licb ON lic.id < licb.id and lic.user=licb.user SET lic.active=0 where lic.user IN (select user from ( select License.user from License where License.active = 1 and License.user="c592f791-5e9d-4f95-857b-544bdae7180e" and License.startDate <= now() and License.expiryDate >= now() GROUP BY License.user HAVING COUNT(*)>1) as alias_License)
