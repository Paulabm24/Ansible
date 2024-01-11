Como la mayoría del software para administrar configuración, Ansible distingue dos tipos de servidores: controladores y nodos. Primero, está una única máquina de control donde la orquestación comienza. Los nodos son manejados desde esa máquina de control por SSH. La máquina de control conoce a los nodos a través de un inventario.

Para organizar los nodos, Ansible despliega módulos a los nodos el protocolo SSH. Los módulos son guardados temporalmente en los nodos y se comunican con la máquina de control a través del protocolo JSON sobre una salida estándar.Como Ansible no controla los módulos ya que estos se ejecutan en la máquina remota, no consumen recursos locales porque no existen procesos o programas ejecutándose en segundo plano.

En contraste con otros programas de control de configuración como Chef y Puppet, Ansible usa una arquitectura sin agentes Con la arquitectura basada en agentes, los nodos deben instalar localmente un proceso de comunicaciones con la máquina de control. Con la arquitectura sin agentes los nodos no necesitan instalar ni ejecutar en segundo plano ningún proceso que se comunique con la máquina de control. Este tipo de arquitectura reduce la sobrecarga de la red y previene el uso de estrategias de control más agresivas por parte del servidor (como puede ser la realización de sondeos, con sus constantes operaciones de consulta).

El diseño de Ansible​ incluye:

- Mínimo por naturaleza. Los sistemas de administración no deben imponer dependencias adicionales.
  
- Consistente.
  
- Seguro. Ansible no instala agentes vulnerables en los nodos. Solamente se requiere OpenSSH que es considerado crítico y altamente comprobado.
  
- Alta confiabilidad. El modelo de idempotencia es aplicado para las instalaciones y configuraciones, para prevenir efectos secundarios en la ejecución repetitiva de guiones (scripts).
  
- Suave curva de aprendizaje. Los playbooks o libretos usan un lenguaje descriptivo simple, basado en YAML.
