# Bearbeiten von Hausübungen mit IntelliJ

## Dateianzeige

* Am linken Rand finden Sie den Abschnitt **"Project"**. Dort befindet sich eine Übersicht der Dateihierarchie des Projektes. Mit den Pfeilen links von Ordnern/Verzeichnissen können Sie die Ansicht erweitern bzw. verkleinern.
* In dem Verzeichnis **src/main/java** schreiben Sie den eigentlich Code.
* In dem Verzeichnis **src/test/java** schreiben Sie Ihre Tests.

## Neue Dateien erstellen

* Mit einem Rechtsklick auf ein Package können Sie über **new -> Java Class** eine neue Java Datei erstellen. Geben Sie dafür den Namen an, wählen Sie aus, ob es eine Klasse, Interface, Enum oder Annotation sein soll und bestätigen Sie das Erstellen, indem Sie **Enter** drücken.
* Sie können auf dieselbe Weise auch packages erstellen. Wählen Sie dafür **"package"** anstatt **"Java Class"** aus.

## Gradle Tasks

* Um die Übersicht mit allen Gradle Task zu öffnen, drücken Sie am rechten oberen Rand auf **"Gradle"**.
    * Alternativ können Sie sich die Gradle Ansicht auch über den Reiter **"View"** anzeigen lassen, indem Sie dann auf **"Tool Windows" -> "Gradle"** gehen.
* Klappen Sie den Ordner, der nach dem Projekt benannt ist, sowie den darin enthaltenen Ordner **"Tasks"**. Nun sehen Sie alle Verzeichnisse, in denen Gradle Tasks enthalten sind.
* Anbei ist eine Tabelle mit allen relevanten Tasks. Die jeweiligen Tasks sind im Format **"<group-name\>/<task-name\>"** angegeben.
* Sie können eine Task mit einem Doppelklick auf sie ausführen.

| Gradle Task                  | Beschreibung                                                |
|------------------------------|-------------------------------------------------------------|
| application/run              | Führt die main Methode des Projektes aus                    |
| verification/test            | Führt Ihre selbstgeschriebenen Tests aus                    |
| verification/graderPublicRun | Führt die von uns zur Verfügung gestellten public Tests aus |
| verification/check           | Führt alle (selbstgeschriebenen + public) Tests aus         |
| build/mainBuildSubmission    | Erstellt die Abgabedatei im Ordner build/libs               |
| build/assemble               | Erstellt eine ausführbare Datei in build/libs               |
| build/build                  | Führt assemble und check aus                                |

## Code ausführen

* In IntelliJ gibt es verschiedene Methoden, wie Sie Ihren Code ausführen können. Sie können eine der folgenden Methoden benutzten:
    1. Wenn Sie eine Klasse mit einer main Methode betrachten, befindet sich bei der Zeilenangabe auf der Höhe der main Methode und der Klassendefinition ein grünes Dreieck. Wenn Sie auf dieses draufdrücken und dann auf **"Run '...'"** drücken.
    2. Machen Sie links in der Project Ansicht einen Rechtsklick auf eine Klasse mit einer main Methode und drücken Sie auf **"Run '...'"**.
    3. Führen Sie am rechten oberen Rand in der Gradle Ansicht die Task **"run"** im Ordner **"application"** aus.
    4. Drücken Sie am oberen rechten Rand auf das grüne Dreieck.
        * Beachten Sie, dass diese Methode die letzte Aktion erneut ausführt. Diese ist nicht zwangsläufig immer das Ausführen des Codes.
* Wenn Ihr Code nicht terminiert, können Sie das Programm mit dem roten Quadrat am linken Rand stoppen.

## Tests ausführen

* Sie können Ihre Tests auf dieselbe Weise ausführen, wie Ihren Code.
    * Anstelle der Gradle Test **"application/run"** müssen Sie die Task **"verification/test"** ausführen.
    * Wenn Sie in der Project Ansicht einen Rechtsklick auf einen höher liegendes Package bzw. Verzeichnis machen, können Sie alle Test, die in diesem enthalten sind, auf einmal ausführen.

## Fehler und Warnungen erkennen und beheben

* IntelliJ zeigt Ihnen Syntaxfehler in Ihrem Code rot unterstrichenen an. Diese müssen behoben werden.
* Warnungen werden Ihnen gelb unterstrichen angezeigt. Diese müssen zwar nicht behoben werden, sollten es aber.
* Wenn Sie mit der Maus über den rot oder gelb unterstrichenen Text gehen, wird Ihnen eine Beschreibung des Problems, sowie Vorschläge, wie es automatisch behoben werden kann, angezeigt.
* Am unteren linken Rand finden Sie im Abschnitt **"Problems"** eine Übersicht mit allen Fehlern und Warnungen.

## Fehlermeldungen verstehen

* Wenn Sie Ihr Programm ausführen, öffnet sich unten automatisch eine Übersicht über den Verlauf des Programms und die Konsole. Hier werden Ihnen auch die Fehler angezeigt, die während dem Programmablauf auftreten.
* Damit Ihnen die vollständigen Fehlermeldungen angezeigt werden, wählen Sie links von der Konsole die zweite Option von oben aus.
* Eine Fehlermeldung sieht z.B. wie folgt aus:

!!! error "Fehler"
    Exception in thread "main" java.lang.ArithmeticException: / by zero
    at example.Divider.divide(Main.java:20)
    at example.Main.main(Main.java:10)

* Diese Fehlermeldung sagt Ihnen Folgendes:
    * Es ist eine **ArithmeticException** aufgetreten.
    * Der Grund ist: **"/ by zero"**.
    * Der Fehler ist in der Methode **divide** der Klasse **Divider** in Zeile 20 aufgetreten.
    * Diese Methode wurde von der Methode **main** der Klasse **Main** in Zeile 10 aufgerufen.

## Den Debugger benutzten

* IntelliJ bietet Ihnen mit dem Debugger eine sehr hilfreiche Methode Fehler in Ihrem Code zu finden. Sie können den Debugger genauso starten, wie Sie Ihren Code mit den Methoden 1. 2. und 4. ausführen. Der Unterschied dabei ist, dass Sie anstatt auf das grüne Dreieck **"Run '...'"** auf den roten Käfer **"Debug '...'"** drücken müssen.
* Mit einem Linksklick direkt neben der Zeilenangabe können Sie einen Breakpoint erstellen, welcher als roter Punkt angezeigt wird.
* Wenn Sie den Debugger starten, wird er Ihren Code so lange normal ausführen, bis er an einem Breakpoint ankommt. In dem Fall wird das Programm angehalten und Ihnen wird eine Liste der Variable mit den zugehörigen Werten angezeigt.
   * Mit **F8** können Sie die momentane Zeile ausführen.
   * Mit **F7** können Sie die in die Methode, die als nächstes ausgeführt wird, hineinspringen.
   * Mit **F9** können Sie das Programm bis zum nächsten Breakpoint weiterlaufen lassen.
   * Mit **Shift + F8** können Sie das Programm weiterlaufen lassen, bis die momentane Methode verlassen wird.
   * alternativ können Sie dies auch mit den Pfeilen am oberen Rand der Debugger Anzeige machen.
