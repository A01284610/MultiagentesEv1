# MultiagentesEv1

**A. Describe la situación y/o problema a simular**
<br>Para esta simulación se trataría de ver como es que con el uso de Roombas se pudiera limpear un cuarto. Para la simulación se utilizarían Roombas no inteligentes que se mueven en direcciones aleatorias y la cantidad de aspiradoras al igual que el porcentaje de suciedad en el suelo pudede ser definido por el usuario.


**B. Describe los agentes involucrados así como sus acciones y percepciones**
- Roomba
  - Este agente busca en sus celdas vecinas suciedad (considerando las diagonales). Si es que encuentra un agente de _Dirt_ entonces se mueve a esta celda y limpea la suciedad removiendo el agente. Si es que no encuentra suciedad a su alredeor el robot se moverá en una dirección aleatoria en sus vecinos.
- Dirt
  - Este agente no percibe nada del ambiente, también no actua sobre otros agentes. Esta hecho para que sea inicilizado en diferentes celdas y el agente de Roomba lo pueda usar para diferenciar una celda sucia de una limpea. Sin emabrgo, para la creación de estos agentes se toma en consideración un porcentaje de suciedad que el usuario desea. También, debido a que se decidió que la fila superior era exlusivamente para Roombas este Dirt no puede aparecer en esta fila.


**C. Describe cómo interactúan y se comunican dos o más agentes del mismo**
- Roomba
  - En el caso del Roomba estos al moverse en una dirección revisan que no esten moviendose sobre otro _Roomba_ para no eliminarlo. Si es que encuentra que se quiere mover a la posición en la que ya se encuentra un _Roomba_ entonces se utiliza la función move_to_empty().
  - En cuanto a la interacción con el agente _Dirt_ el Roomba busca por estos agentes en su alrededor, si es que lo encuentra entoces se guarda la posición del _Dirt_, este agente de suciedad es eliminado y el _Roomba_ se mueve a la posición guardada.


**D. Describe el entorno**
- Room
  - El modelo del cuarto funciona con una matriz de tamaño definido por el usuario. Se definen variables para el funcionamiento, después se corre el metodo reset(). Aqui se crea la matriz del tamaño definido y un schedule (este nos ayudará con el procesamiento de los pasos). Se utiliza un arrgelo para instanciar los Roombas en la fila superior de la matriz. Al igual que un recorrido de la matriz para posicionar la suciedad. Aparte contiene el metodo step para actualizar los agentes. Finalmente tiene el metodo get_grid() que ayuda con la visualización de la información. Aqui una matriz se llenan con integers 0,1 o 2, según el tipo de agente, estos luego serán procesados para visualizar la matriz con colores.

**E. Identifica  las  variables  y  los  parámetros  que  determinan  el  funcionamiento  del sistema.**
- Runtime
  - GRID_SIZE
  - ROOMBA_COUNT
  - DIRT_PERCENT
- Modelo
  - self.width = width
  - self.height = height
  - self.roombaCount = roombaNum
  - self.dirtChance = dirtPercent
  - self.dirtCount = 0
- Roomba
  - self.dirtCount = 0
  - self.battery = 100
  - self.nextPos = None
- Dirt 
  - _No se utilizan variables para el funcionamiento_


**F. Describe el proceso de simulación**


**G. Discute clara y concisamente los resultados obtenidos**


**H. Agrega el link al repositorio.**
