### Cargar datos

[javi@localhost script]$ ./init.sh
🌱 Insertando datos de ejemplo en LocalStack...
📦 Insertando productos de ejemplo...
✅ Productos de ejemplo insertados
💬 Insertando comentarios de ejemplo...
✅ Comentarios de ejemplo insertados
🎉 ¡Datos de ejemplo insertados correctamente!
📋 Datos insertados:
   - 3 productos: Zapatillas Running Pro, Botas Montaña Explorer, Sandalias Verano Comfort
   - 3 comentarios: 1 positivo, 1 negativo, 1 neutral

🔗 Acceso a LocalStack: http://midominio.local


### Evidencias

aws dynamodb scan   --table-name la-huella-comments   --endpoint-url=http://midominio.local


aws dynamodb scan   --table-name la-huella-products   --endpoint-url=http://midominio.local


### Desplegar aplicación

En el servicio de backend, agregar:

   extra_hosts:
      - "midominio.local:192.168.0.19"

docker compose up -d

Entrar en la aplicación con ventana privada de firefox --> ttp://172.27.0.1/


### Consulta tablas

[javi@localhost eu-devops-7-la-huella-main-etapa4]$ aws dynamodb scan \
  --table-name la-huella-comments \
  --endpoint-url=http://midominio.local
{
{
    "Items": [
        {
            "sentiment": {
                "S": "positive"
            },
            "sentimentScore": {
                "N": "0.89"
            },
            "createdAt": {
                "S": "2024-01-20T14:30:00Z"
            },
            "processed": {
                "BOOL": true
            },
            "productId": {
                "S": "prod-001"
            },
            "rating": {
                "N": "5"
            },
            "comment": {
                "S": "Excelentes zapatillas, muy cómodas para correr largas distancias. Las recomiendo totalmente."
            },
            "id": {
                "S": "comment-001"
            },
            "userName": {
                "S": "María García"
            },
            "userId": {
                "S": "user-001"
            }
        },
        {
            "sentiment": {
                "S": "negative"
            },
            "sentimentScore": {
                "N": "0.12"
            },
            "createdAt": {
                "S": "2024-01-21T09:15:00Z"
            },
            "processed": {
                "BOOL": true
            },
            "productId": {
                "S": "prod-001"
            },
            "rating": {
                "N": "1"
            },
            "comment": {
                "S": "El producto llegó defectuoso, la suela se despegó después de una semana. Muy decepcionado."
            },
            "id": {
                "S": "comment-002"
            },
            "userName": {
                "S": "Carlos Ruiz"
            },
            "userId": {
                "S": "user-002"
            }
        },
        {
            "sentiment": {
                "S": "neutral"
            },
            "sentimentScore": {
                "N": "0.55"
            },
            "createdAt": {
                "S": "2024-01-22T16:45:00Z"
            },
            "processed": {
                "BOOL": true
            },
            "productId": {
                "S": "prod-002"
            },
            "rating": {
                "N": "3"
            },
            "comment": {
                "S": "Las botas están bien, cumplen su función pero esperaba mejor calidad por el precio."
            },
            "id": {
                "S": "comment-003"
            },
            "userName": {
                "S": "Ana López"
            },
            "userId": {
                "S": "user-003"
            }
        }
    ],
    "Count": 3,
    "ScannedCount": 3,
    "ConsumedCapacity": null
}

[javi@localhost eu-devops-7-la-huella-main-etapa4]$ aws dynamodb scan \
  --table-name la-huella-products \
  --endpoint-url=http://midominio.local
{
{
    "Items": [
        {
            "sentiment": {
                "S": "positive"
            },
            "sentimentScore": {
                "N": "0.89"
            },
            "createdAt": {
                "S": "2024-01-20T14:30:00Z"
            },
            "processed": {
                "BOOL": true
            },
            "productId": {
                "S": "prod-001"
            },
            "rating": {
                "N": "5"
            },
            "comment": {
                "S": "Excelentes zapatillas, muy cómodas para correr largas distancias. Las recomiendo totalmente."
            },
            "id": {
                "S": "comment-001"
            },
            "userName": {
                "S": "María García"
            },
            "userId": {
                "S": "user-001"
            }
        },
        {
            "sentiment": {
                "S": "negative"
            },
            "sentimentScore": {
                "N": "0.12"
            },
            "createdAt": {
                "S": "2024-01-21T09:15:00Z"
            },
            "processed": {
                "BOOL": true
            },
            "productId": {
                "S": "prod-001"
            },
            "rating": {
                "N": "1"
            },
            "comment": {
                "S": "El producto llegó defectuoso, la suela se despegó después de una semana. Muy decepcionado."
            },
            "id": {
                "S": "comment-002"
            },
            "userName": {
                "S": "Carlos Ruiz"
            },
            "userId": {
                "S": "user-002"
            }
        },
        {
            "sentiment": {
                "S": "neutral"
            },
            "sentimentScore": {
                "N": "0.55"
            },
            "createdAt": {
                "S": "2024-01-22T16:45:00Z"
            },
            "processed": {
                "BOOL": true
            },
            "productId": {
                "S": "prod-002"
            },
            "rating": {
                "N": "3"
            },
            "comment": {
                "S": "Las botas están bien, cumplen su función pero esperaba mejor calidad por el precio."
            },
            "id": {
                "S": "comment-003"
            },
            "userName": {
                "S": "Ana López"
            },
            "userId": {
                "S": "user-003"
            }
        }
    ],
    "Count": 3,
    "ScannedCount": 3,
    "ConsumedCapacity": null
}



[javi@localhost eu-devops-7-la-huella-main-etapa4]$ aws dynamodb scan   --table-name la-huella-products   --endpoint-url=http://midominio.local
{
{
    "Items": [
        {
            "createdAt": {
                "S": "2024-01-16T11:00:00Z"
            },
            "price": {
                "N": "129.99"
            },
            "imageUrl": {
                "S": "https://example.com/hiking-explorer.jpg"
            },
            "name": {
                "S": "Botas Montaña Explorer"
            },
            "description": {
                "S": "Botas resistentes para montaña con membrana impermeable"
            },
            "id": {
            "imageUrl": {
                "S": "https://example.com/hiking-explorer.jpg"
            },
            "name": {
                "S": "Botas Montaña Explorer"
            },
            "description": {
                "S": "Botas resistentes para montaña con membrana impermeable"
            },
            "id": {
                "S": "prod-002"
            },
            "category": {
                "S": "hiking"
            }
        },
        {
            "createdAt": {
                "S": "2024-01-17T12:00:00Z"
            },
            "price": {
                "N": "45.99"
            },
            "imageUrl": {
                "S": "https://example.com/summer-comfort.jpg"
            },
            "name": {
                "S": "Sandalias Verano Comfort"
            },
            "description": {
                "S": "Sandalias cómodas para el verano con suela ergonómica"
            },
            "id": {
                "S": "prod-003"
            },
            "category": {
                "S": "casual"
            }
        },
        {
            "createdAt": {
                "S": "2024-01-15T10:00:00Z"
            },
            "price": {
                "N": "89.99"
            },
            "imageUrl": {
                "S": "https://example.com/running-pro.jpg"
            },
            "name": {
                "S": "Zapatillas Running Pro"
            },
            "description": {
                "S": "Zapatillas profesionales para running con tecnología de amortiguación avanzada"
            },
            "id": {
                "S": "prod-001"
            },
            "category": {
                "S": "running"
            }
        }
    ],
    "Count": 3,
    "ScannedCount": 3,
    "ConsumedCapacity": null
}







