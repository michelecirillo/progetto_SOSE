# Progetto SOSE

## Installation
  
1. Installa il software di modellazione [Eclipse Modeling Project](https://projects.eclipse.org/projects/modeling)
1. Importa in eclipse i packages necessari:
    1. Scarica il pacchetto dei packages necessari da [qui](https://github.com/occiware/ecore)
    1. Unzip del file `ecore-master.zip`
    1. In Eclipse `File->Open Projects From File System...->Directory->[/path/to/ecore-master/]->Finish`
1. Pull di questa repository: `git clone https://github.com/michelecirillo/progetto_SOSE.git`
1. Importa tutti i metamodelli della cartella `/model` facendo tasto destro sulla cartella di root del progetto `->Properties->QVT Settings->Metamodel mappings->Add` 
1. (Facoltativamente) Installa [Papyrus](https://www.eclipse.org/papyrus/download.html)

---

## Content

Questo progetto contiene le seguenti directory:
- `/model`:  
	Contiene tutti i metamodelli non di default da importare al fine di poter eseguire la trasformazione, in particolare il metamodello `Infrastructore.ecore`
- `/models`:  
	Contiene i modelli di input e output della trasformazione
- `/tests`:  
	Contiene file di test
- `/trasformations`:  
	Contiene i file QVT che specificano la trasformazione

### Directory Structure

```
progetto_SOSE/
├── build.properties
├── Deployment diagram to Infrastructure.launch
├── model/
│   ├── Infrastructure.ecore
│   ├── Infrastructure.genmodel
│   └── Infrastructure.occie
├── models/
│   ├── configuration.Infrastructure
│   ├── deployment_diagram.di
│   ├── deployment_diagram_it_IT.properties
│   ├── deployment_diagram.notation
│   ├── deployment_diagram.uml
│   ├── infrastructure.profile.uml
│   └── representations.aird
├── plugin.xml
├── README.md
├── tests/
│   ├── My.Infrastructure
│   └── representations.aird
└── transforms/
    └── deployment2occi.qvto
```

---

## Usage

1. In `/models` modifica il file `deployment_diagram.di` nel caso utilizzi papyrus, `deployment_diagram.uml` altrimenti
    1. Modifica, elimina o aggiungi nodi e communication paths
    1. Aggiungi il profilo Infrastructure (OCCI) ai nodi aggiunti:
        * Tasto destro sul nuovo nodo->`Profiles->Update profiles...`
            * `Profile: infrastructure`
            * `Stereotype: [compute/network/storage]` a seconda del tipo di nodo
        * `OK`
1. In `/progetto_SOSE` tasto destro su `Deployment diagram to Infrastructure.launch->Run as->Deployment diagram to Infrastructure`
1. Troverai il file `configuration.Infrastructure` corrispondente la trasformazione appena eseguita sotto `/models`
