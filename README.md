Wird in der DevOps-Factory zwischen transienten und persistenen "Instanzen" unterschieden?
  -  z.B. im DEV-Cluster könnte des transiente Instanzen geben von AgroCD die nujr kurz für einen Zweck da sind
  -  z.B. im Test-Cluster sollten alle "Instanzen" persinstent sein.

Generell sollte die Frage diskutiert werden ob transiente "Umgebungen, Instanzen oder WasAuchImmer" überhaupt unter das Thema "GitOps" fallen sollten. Sind das nur "DevOps" Objekte
  -  Das Konzept DevOps ist hier etwas anderes.

Auch Kontext von "feature-Driven" etc. kann also eine vergängliche Umgebung erzeugt werden zu Testzweckes oder oder oder

Was ist devOps was ist GitOps im Wiki für PNR beschreiben. Hat das die DevOps Factory beschrieben.

Sollten explizit sagen das alle unsere Testumgebungen quasi persistente, permanente "Enviroments" sind?

In GitOps sind aber nicht die "Umgebungen" wichtig sondern die "Cluster"( OCP-Instanzen).

Eine ArgoCD pro Cluster. Alles was einen CLuster angeht ist auf einem Fleck. ArgoCD braucht nur zugriff auf dem Cluster wo es drin ist = Sicherheit
  Eine ArgoCD Instanze die  alles macht kann ein SIchheitsproblem sein. Es ist aber einfacher nur "einer" Instanze zu warten. Wenn wir 1000000 Deployments in ArgoCD haben geht ggf die performance in Arsch


Wir brauchen mindestens 2 "REPOS":
  1. Applikations-Repo: Sourcen, Docker + "statik" Helm Manifests/Charts
  2. Ein "desired State"-Repo für eine "Umgebung" 

Branches dürfen kein Mittel für eine logische Strukturierung sein. Branches sind dazu da in main gemerged zu werden. Kein Branch einer "staging" wir ja auch den main gemerged wenn der main die Produktion ist, da ja sonst "staging" Werte in die Produktion gehen würden.
Daraus folgt direkt das jedes "permanente" Objekt ein eigenes Repo/Verzeichnis braucht.


