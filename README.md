# aws-cdk-playground-python

El objetivo es preparar el entorno para trabajar con AWS CDK con Python.

## Instalación y preparación de AWS CDK

1. En caso de no tener nodejs, instalar con asdf:
```bash
   asdf plugin add nodejs https://github.com/asdf-vm/asdf-nodejs.git
   asdf install nodejs 22.11.0
```

![imagen](https://github.com/user-attachments/assets/e663ed6b-6832-4e60-a31a-732152286f9b)

3. Verificar la instalación:
   ```bash
   cdk --version
   ```

![imagen](https://github.com/user-attachments/assets/9e9c5911-f60c-44a0-9502-f3bdb68f9da1)

4. Preparar el directorio del proyecto:
   ```bash
   mkdir cdk-iam-lab
   cd cdk-iam-lab
   ```

5. Inicializar proyecto CDK con Python:
   ```bash
   cdk init app --language python
   ```

![imagen](https://github.com/user-attachments/assets/4b2ef823-86a2-4286-83a1-b72907d16f65)

6. Inicializad el entorno de CDK en vuestra cuenta de AWS:
   ```bash
   cdk bootstrap
   ```

7. Instalar dependencias del proyecto:
   ```bash
   pip install -r requirements.txt
   ```

## Creación de Usuario IAM y Grupo con AWS CDK

El objetivo es crear un usuario IAM con permisos de PowerUserAccess usando CDK con Python.

1. Reemplazar el contenido de `cdk_iam_lab/cdk_iam_lab_stack.py` con el fichero de este repositorio


   ```python
   from aws_cdk import (
       Stack,
       CfnOutput,
       aws_iam as iam
   )
   from constructs import Construct

   class CdkIamLabStack(Stack):
       def __init__(self, scope: Construct, construct_id: str, **kwargs) -> None:
           ...

   ```

2. Sintetizar el template CloudFormation:
   ```bash
   cd ..
   cdk synth > cf.yaml
   ```

3. Desplegar la infraestructura:
   ```bash
   cdk deploy
   ```

4. Descomentad el output y volved a desplegar para ver un update.

5. Capturar los outputs del despliegue con los detalles del usuario

6. Enviar un email al profesor con:
   - Captura del despliegue correcto
   - Evidencia de la creación del usuario y grupo en la consola de AWS
   - URL al repositorio con el código en github

Referencias:
- [AWS CDK Python Reference](https://docs.aws.amazon.com/cdk/api/v2/python/)
- [CDK Workshop for Python](https://cdkworkshop.com/30-python.html)

