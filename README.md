# Observateur d'Événements Windows
# Configuration d'une vue personnalisée pour surveiller le service DNS sous Windows Server

## Étapes de configuration

1. **Créer une machine virtuelle Windows Server**  
   - Installer Windows Server sur VirtualBox, VMware ou Hyper-V.  
   - Configurer les paramètres réseau et administratifs.

2. **Installer le rôle DNS**  
   - Ouvrir le **Gestionnaire de serveur**.  
   - Ajouter le rôle **Serveur DNS** via **Ajouter des rôles et fonctionnalités**.  
   - Suivre l’assistant d’installation et valider la configuration.

3. **Créer une vue personnalisée dans l'Event Viewer**  
   - Ouvrir l'**Observateur d’événements** (`eventvwr.msc`).  
   - Aller dans **Journaux Windows** > **Système**.  
   - Cliquer sur **Créer une vue personnalisée**.  

## Critères de filtrage

### **Niveaux à surveiller**  
- 🔴 **Critique (1)**  
- ❌ **Erreur (2)**  
- ⚠️ **Avertissement (3)**  
- ℹ️ **Information (4)** _(suivi des démarrages/arrêts)_  

### **Sources d’événements à inclure**  
- **DNS-Server-Service** : Opérations du serveur DNS  
- **DNS Client Events** : Événements liés aux clients DNS  

### **ID d'événements principaux**  
| ID | Description |
|----|------------|
| 2 | Démarrage du serveur DNS |
| 4 | Arrêt du serveur DNS |
| 409 | Erreur de résolution de nom |
| 501-502 | Échec de chargement de zone |
| 6001-6002 | Problèmes de réplication DNS |

## 🧐 Critères d’acceptation  
✔️ Configurer la vue personnalisée dans l’Event Viewer avec les critères demandés.  
✔️ Attribuer un **nom descriptif** à la vue personnalisée.  
✔️ Exporter la vue au **format XML**.  
✔️ Ajouter le fichier XML sur un dépôt **GitHub** accompagné d’un **README** expliquant la configuration.

## 📂 Dépôt GitHub  
Ajoute le fichier **XML** généré ainsi qu’un **README.md** décrivant la configuration et son utilité.

---

📌 **Astuce** : Pour exporter la vue, après l’avoir créée, fais un clic droit sur la vue personnalisée > **Exporter la vue personnalisée...** et enregistre-la sous format `.xml`.
