# Laboratorio: Firma Digital con OpenSSL

Este proyecto documenta un laboratorio práctico de ciberseguridad realizado en entorno Linux (CyberOps Workstation de Cisco NetAcad) utilizando OpenSSL para aplicar criptografía asimétrica mediante firmas digitales.

## 🎯 Objetivo
Aplicar firmas digitales para:
- Generar claves criptográficas (privada y pública)
- Firmar digitalmente un archivo
- Verificar autenticidad e integridad del archivo
- Detectar alteraciones no autorizadas

## 🧪 Comandos utilizados

```bash
openssl genpkey -algorithm RSA -out private_key.pem
openssl rsa -pubout -in private_key.pem -out public_key.pem
echo "Documento oficial: Presupuesto 2025 aprobado." > documento.txt
openssl dgst -sha256 -sign private_key.pem -out firma.bin documento.txt
openssl dgst -sha256 -verify public_key.pem -signature firma.bin documento.txt
nano documento.txt  # Simulación de modificación
openssl dgst -sha256 -verify public_key.pem -signature firma.bin documento.txt
```

## 📁 Estructura del proyecto

```
firma-digital-lab/
├── README.md
├── docs/
│   ├── Lab_FirmaDigital_Guia_Practica.docx
│   └── FirmaDigital_Evidencia.png
├── claves/
│   ├── private_key.pem
│   └── public_key.pem
├── archivos/
│   ├── documento.txt
│   └── firma.bin
```

## 🔐 Conclusión
Este laboratorio demuestra cómo las firmas digitales permiten validar la integridad de documentos y confirmar su autenticidad mediante el uso de claves RSA, una habilidad esencial en auditoría digital, cumplimiento normativo y seguridad de la información.

---

✅ Proyecto personal en el marco del curso **Cisco Cybersecurity Essentials**.  
🔗 Conéctate conmigo en [LinkedIn](https://www.linkedin.com/in/tu-perfil)
