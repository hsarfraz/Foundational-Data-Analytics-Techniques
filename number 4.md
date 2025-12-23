# PostgreSQL

```
SELECT patient_id,
  ROUND(weight_pounds::numeric / (height_inches::numeric * height_inches::numeric) * 703, 1) AS BMI
FROM patients
WHERE (weight_pounds::numeric / (height_inches::numeric * height_inches::numeric) * 703) >= 30
```

# MSSQL

```
SELECT patient_id,
  ROUND(CAST(weight_pounds AS FLOAT) / (CAST(height_inches AS FLOAT) * CAST(height_inches AS FLOAT)) * 703, 1) AS BMI
FROM patients
  WHERE CAST(weight_pounds AS FLOAT) / (CAST(height_inches AS FLOAT) * CAST(height_inches AS FLOAT)) * 703 >= 30;
```
