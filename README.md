[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-c66648af7eb3fe8bc4f294546bfd86ef473780cde1dea487d3c4ff354943c9ae.svg)](https://classroom.github.com/online_ide?assignment_repo_id=7773452&assignment_repo_type=AssignmentRepo)
# Primer Trabajo de Actuación en Clase
## Consigna

Encontrar los errores en el código de Terraform y corregirlos. El código despliega los siguientes objetos:

* Un VPC
* Dos subnets
* Una instancia EC2
* Una Route Table
* Un Internet Gateway
* Un LoadBalancer, target groups y rules.

## Definición de terminado

El resultado debe ser la web de "Caffé" visualizada desde la url del LoadBalancer obtenida del OUTPUT. 

![caffe img](./img/caffe.png)



--- 
Team Ricardo Sánchez- Martín Pacheco
---


# Comentarios y errores corregidos:

* Faltaba valor default para variable perfil
    * También se modificó valor en archivo .tfvars
* Había que modificar clave ssh para que coincidiera con la almacenada localmente
* En el archivo de instancia se incorporó el subnet ID
* Al Security Group del Load Balancer se le corrigió el puerto. Tenía el 88, se modificó por el 80.
* Se modificó el CIDR de la Route Table para que pudiera salir a cualquier dirección en internet (0.0.0.0/0)


* La creación de los recursos lleva tiempo, si se interrumpe el proceso de creación puede que los mismos no queden reflejados en el archivo de estado, lo que puede ocasionar que al hacer un "terraform destroy" no se eliminen dichos recursos.
