# 🧩 Plugin JetBrains : ContextualSearch

## 🎯 Objectif
Créer un **plugin JetBrains (Kotlin)** permettant d'effectuer une **recherche du texte sélectionné** (dans l'éditeur, le terminal ou les consoles d'exécution) via différents **moteurs de recherche** configurables. L'action est accessible via le **menu contextuel** et les moteurs sont paramétrables dans **Settings → Tools → ContextualSearch**.

---

## ✨ Fonctionnalités

### Recherche contextuelle
- Sélection de texte dans l'**éditeur**, le **terminal** ou les **consoles d'exécution (Run)**
- Menu contextuel "Search with..." avec sous-menu dynamique des moteurs activés
- Ouverture automatique dans le navigateur par défaut

### Configuration des moteurs
- Interface de gestion complète dans **Settings → Tools → ContextualSearch**
- Ajout, modification, suppression de moteurs
- Activation/désactivation individuelle
- Import/Export au format JSON
- Double-clic pour édition rapide

---

## 🗺️ Architecture

### Fichiers principaux

**Configuration :**
- `plugin.xml` - Déclaration du plugin et enregistrement des actions
- `SearchEngine.kt` - Modèle de données (name, url, enabled)
- `SearchSettingsState.kt` - Persistance via PersistentStateComponent
- `SearchSettingsConfigurable.kt` - Intégration dans Settings
- `SearchSettingsPanel.kt` - Interface utilisateur de configuration
- `ImportExportService.kt` - Import/Export JSON

**Actions :**
- `SearchWithEngineAction.kt` - ActionGroup principal avec support multi-contexte
- `TerminalActionRegistrar.kt` - Enregistrement dynamique dans TerminalPopupMenu

---

## 🔧 Implémentation technique

### Support multi-contexte
La récupération du texte sélectionné fonctionne pour :

**Éditeur :**
```kotlin
e.getData(CommonDataKeys.EDITOR)?.selectionModel?.selectedText
```

**Terminal et consoles d'exécution :**
```kotlin
e.getData(PlatformDataKeys.COPY_PROVIDER)?.let {
    CopyPasteManager.getInstance().contents?.getTransferData(DataFlavor.stringFlavor)
}
```

### Enregistrement des actions
```xml
<group id="ContextualSearch.SearchWithEngineAction"
       class="com.jawehrung.contextualsearch.actions.SearchWithEngineAction"
       text="Search with..."
       popup="true">
  <add-to-group group-id="EditorPopupMenu" anchor="last"/>
  <add-to-group group-id="ConsoleEditorPopupMenu" anchor="last"/>
</group>
```

### Modèle de données
```kotlin
data class SearchEngine(
    var enabled: Boolean = true,
    var name: String = "",
    var url: String = ""  // Utilise %s comme placeholder pour la requête
)
```

---

## 🚀 Utilisation

1. **Configuration initiale :**
   - Aller dans **Settings → Tools → ContextualSearch**
   - Ajouter des moteurs de recherche (ex: Google, Stack Overflow, GitHub)
   - Format URL : `https://www.google.com/search?q=%s`

2. **Recherche :**
   - Sélectionner du texte dans l'éditeur, le terminal ou une console
   - Clic droit → **"Search with..."**
   - Choisir le moteur de recherche

3. **Import/Export :**
   - Utiliser les boutons Import/Export dans les paramètres
   - Format JSON pour partager les configurations

---

## 📦 Dépendances
- `com.intellij.modules.platform`
- `org.jetbrains.plugins.terminal` (optionnel)

---

## 🔄 Version actuelle : 0.2.1

### Fonctionnalités implémentées
✅ Configuration des moteurs de recherche
✅ Support éditeur de code
✅ Support terminal
✅ Support consoles d'exécution (Run)
✅ Import/Export JSON
✅ Interface de gestion complète
✅ Enregistrement dynamique dans TerminalPopupMenu
