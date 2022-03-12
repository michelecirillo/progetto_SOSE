# Progetto SOSE

## Installation
  
1. Installa il software di modellazione [Eclipse Modeling Project](https://projects.eclipse.org/projects/modeling)
1. Importa in eclipse i packages necessari:
    1. Scarica il pacchetto dei packages necessari da [qui](https://github.com/occiware/ecore)
    1. Unzip del file `ecore-master.zip`
    1. In Eclipse `File->Open Projects From File System...->Directory->[/path/to/ecore-master/]->Finish`
1. Pull di questa repository: `git clone https://github.com/michelecirillo/progetto_SOSE.git`
1. (Facoltativamente) Installa [Papyrus](https://www.eclipse.org/papyrus/download.html)

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
