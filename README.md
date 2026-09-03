<p align="center">
  <picture>
    <source media="(prefers-color-scheme: dark)" srcset="assets/devops-experts-logo-dark.svg">
    <img alt="DevOps Experts" src="assets/devops-experts-logo.svg" width="340">
  </picture>
</p>

<h1 align="center">חומרי הלימוד שלי — קורס DevOps</h1>

<p align="center">
  <a href="https://devopsexperts.co.il/"><img alt="מכללה" src="https://img.shields.io/badge/%D7%9E%D7%9B%D7%9C%D7%9C%D7%94-DevOps%20Experts-f47425"></a>
  <img alt="מחזור" src="https://img.shields.io/badge/%D7%9E%D7%97%D7%96%D7%95%D7%A8-1125-333">
  <img alt="שיעורים" src="https://img.shields.io/badge/%D7%A9%D7%99%D7%A2%D7%95%D7%A8%D7%99%D7%9D-13-333">
  <img alt="ריפו פרטי" src="https://img.shields.io/badge/%D7%A8%D7%99%D7%A4%D7%95-%D7%A4%D7%A8%D7%98%D7%99-555">
</p>

<div dir="rtl">

## על הריפו הזה

הריפו הזה מרכז את **כל חומר הלימוד מקורס ה‑DevOps שאני עושה במכללת [DevOps Experts](https://devopsexperts.co.il/)**, מחזור **1125**. זה ארכיון אישי ופרטי — הכל במקום אחד כדי שאוכל לחזור לכל שיעור, להריץ מחדש כל תרגיל ולהיזכר בפקודה שכבר עשיתי פעם.

המכללה מתמחה בהכשרות מעשיות ואינטנסיביות בתחומי DevOps, ארכיטקטורת תוכנה, הנדסת AI ו‑Python, עם דגש על תרגול מעשי בכיתות קטנות. הקורס עצמו רץ מנובמבר 2025 עד אוגוסט 2026 וכיסה את כל שרשרת ה‑DevOps: מיסודות Linux, דרך קונטיינרים, Kubernetes, Helm, CI/CD ו‑GitOps, ועד ניטור, AWS, Terraform ו‑Ansible.

## איך זה בנוי — מספר הסקריפט = מספר השיעור

הלב של הריפו הוא תיקיית [`scripts/`](scripts/). **כל סקריפט מתאים לשיעור אחד, לפי המספר שלו** — `1.sh` זה שיעור 1, `2.sh` זה שיעור 2, וכן הלאה. הסקריפטים הם לא סקריפטים להרצה אוטומטית אלא **יומן פקודות של השיעור**: הפקודות שהועברו בכיתה לפי הסדר, עם הערות, קישורים ותרגילי הכיתה שניתנו בסוף.

שאר התיקיות הן קבצי העזר שהסקריפטים מפנים אליהם — מניפסטים של Kubernetes, צ'ארטים של Helm, וורקפלואים, פלייבוקים וקוד Terraform.

## מפת השיעורים

| # | סקריפט | נושא השיעור | קבצים נלווים |
|---|---|---|---|
| 1 | [`scripts/1.sh`](scripts/1.sh) | יסודות Linux בתוך קונטיינר | — |
| 2 | [`scripts/2.sh`](scripts/2.sh) | Docker לעומק | — |
| 3 | [`scripts/3.sh`](scripts/3.sh) | Kubernetes — יסודות | [`k8s/`](k8s/) |
| 4 | [`scripts/4.sh`](scripts/4.sh) | Kubernetes — אחסון, קונפיגורציה ו‑Workloads | [`k8s/volumes/`](k8s/volumes/) |
| 5 | [`scripts/5.sh`](scripts/5.sh) | Helm | [`argocd/ex2/mychart/`](argocd/ex2/mychart/) |
| 6 | [`scripts/6.sh`](scripts/6.sh) | Git ו‑GitHub | — |
| 7 | [`scripts/7.sh`](scripts/7.sh) | GitHub Actions | [`github-workflows/`](github-workflows/) |
| 8 | [`scripts/8.sh`](scripts/8.sh) | ArgoCD ו‑GitOps | [`argocd/`](argocd/) |
| 9 | [`scripts/9.sh`](scripts/9.sh) | ניטור — Prometheus ו‑Grafana | [`monitoring/`](monitoring/) |
| 10 | [`scripts/10.sh`](scripts/10.sh) | AWS ראשוני + Terraform ראשוני | — |
| 11 | *(אין סקריפט)* | Terraform מתקדם | [`terraform/`](terraform/) |
| 12 | [`scripts/12.sh`](scripts/12.sh) | Serverless — Lambda, SQS, DynamoDB | — |
| 13 | [`scripts/13.sh`](scripts/13.sh) | שירותי AWS מנוהלים — סודות, פרמטרים, RDS | — |
| 14 | [`scripts/14.sh`](scripts/14.sh) | Ansible | [`ansible-demo/`](ansible-demo/) |

> **לגבי שיעור 11:** אין קובץ `11.sh` בריפו. תיקיית [`terraform/`](terraform/) מכילה ארבעה תרגילים ברמה גבוהה בהרבה ממה שהופיע בשיעור 10, אז סביר מאוד שהם שייכים לשיעור הזה — אבל זו הסקה שלי מהתוכן, לא משהו שכתוב במפורש.

---

## פירוט מלא — שיעור אחרי שיעור

### שיעור 1 — יסודות Linux בתוך קונטיינר

הקמת סביבת עבודה בטוחה (`docker run --name devops-sandbox ubuntu`) ואז כל הבסיס של שורת הפקודה: ניווט בין תיקיות, יצירה והעברה של קבצים, קלט/פלט והפניות (`>` מול `>>`), משתני סביבה ו‑`export`, קודי יציאה (`$?`) והתקנת חבילות עם `apt`.

הסיום הוא החלק שהכי שימושי בפועל — **עיבוד לוגים בשרשרת pipe**: לוקחים את `/var/log/dpkg.log`, מסננים ב‑`grep`, שולפים שדה ב‑`awk` וחותכים אותו ב‑`cut`. זו התבנית שחוזרת בכל עבודת DevOps אמיתית.

### שיעור 2 — Docker לעומק

ארבעה בלוקים נפרדים בשיעור אחד:

1. **מחזור חיים של קונטיינר** — `run`, `exec`, `ps`, `stop`, `start`, `rm -vf`, ומיפוי פורטים.
2. **בניית אימג' משלך** — אפליקציית Flask קטנה שקוראת משתנה סביבה, `Dockerfile` שמתקין את התלויות, ואז `build` ו‑`run`.
3. **רשתות ו‑Compose** — יצירת רשת ייעודית והוכחה שקונטיינרים מוצאים זה את זה **לפי שם** (`curl http://container2`), ואז אותו רעיון בצורה מוצהרת ב‑`docker-compose.yaml`. בסוף: `tag` ו‑`push` ל‑Docker Hub.
4. **Multi-stage build** — אותה אפליקציית Go נבנית פעמיים, פעם ב‑`Dockerfile.heavy` (תמונת golang מלאה) ופעם ב‑`Dockerfile.slim` (שלב build נפרד ואז העתקה ל‑alpine). ההשוואה בין הגדלים היא כל הפואנטה.

### שיעור 3 — Kubernetes, יסודות

מ‑`kubectl config use-context` ועד אפליקציה שרצה:

- **התמצאות** — namespaces, `get pods --all-namespaces`, `describe node`
- **Pod בודד** לעומת **Deployment** — ומה ה‑ReplicaSet עושה באמצע
- **שינויים חיים** — `scale` ל‑20 רפליקות, `set image`, וצפייה ב‑rollout דרך `watch kubectl get pods`
- **רשת** — ClusterIP מול NodePort מול `port-forward`, ומתי משתמשים בכל אחד
- **מעבר ל‑YAML** — מניפסט שמגדיר Service עם שני פורטים בשם + שני Pods, ואז [`k8s/examples.yaml`](k8s/examples.yaml) ו‑[`k8s/crontab.yaml`](k8s/crontab.yaml)

### שיעור 4 — Kubernetes: אחסון, קונפיגורציה ו‑Workloads

השיעור הזה כולו נשען על [`k8s/volumes/`](k8s/volumes/), וכל קובץ שם הוא שלב בסיפור:

| נושא | קבצים |
|---|---|
| אחסון מתמיד | [`pv.yaml`](k8s/volumes/pv.yaml), [`pvc.yaml`](k8s/volumes/pvc.yaml), [`pod-with-pvc.yaml`](k8s/volumes/pod-with-pvc.yaml) |
| אחסון זמני | [`pod-empty-dir.yaml`](k8s/volumes/pod-empty-dir.yaml) |
| קונפיגורציה | [`config-map.yaml`](k8s/volumes/config-map.yaml), [`game-config.yaml`](k8s/volumes/game-config.yaml), [`pod-with-config-map.yaml`](k8s/volumes/pod-with-config-map.yaml) |
| סודות | [`secret.yaml`](k8s/volumes/secret.yaml), [`pod-with-secret.yaml`](k8s/volumes/pod-with-secret.yaml) |
| Workloads נוספים | [`statefulset.yaml`](k8s/volumes/statefulset.yaml), [`daemonset.yaml`](k8s/volumes/daemonset.yaml), [`cronjob.yaml`](k8s/volumes/cronjob.yaml) |

הרגע החשוב בשיעור: כותבים `index.html` לתוך ה‑volume מתוך ה‑Pod, מוחקים את ה‑Pod, ומוכיחים שהקובץ עדיין שם. בסוף נזכרים גם PodDisruptionBudget, PriorityClass ו‑ResourceQuota.

### שיעור 5 — Helm

מ‑`helm create` ועד צ'ארט שמפורסם ל‑registry:

- **אנטומיה של צ'ארט** — `values.yaml`, `templates/_helpers.tpl`, ההבדל בין `version` ל‑`appVersion` ב‑`Chart.yaml`, ו‑`NOTES.txt`
- **לראות לפני שמריצים** — `helm template`, `--debug`, `helm lint`, `--dry-run`, והפלאגין [helm-diff](https://github.com/databus23/helm-diff)
- **גרסאות ו‑rollback** — `helm history`, `helm rollback`, `--atomic`, וההצצה מאחורי הקלעים: Helm שומר כל revision כ‑Secret ב‑Kubernetes (`kubectl get secrets`)
- **ערכים חיצוניים** — `values-prod.yaml` דרך `-f`, והכלל ש‑`--set` תמיד גובר על `-f`
- **פרסום וצריכה** — `helm package`, התחברות ל‑OCI registry ו‑`helm push`, ואז משיכת צ'ארטים של אחרים מ‑[ArtifactHub](https://artifacthub.io/) ו‑dependencies/subcharts

**תרגיל כיתה:** לבנות צ'ארט עם 5 רפליקות של `nginx:alpine`, לארוז, לדחוף ל‑Docker Hub, למחוק את ההתקנה המקומית ולהתקין מחדש מה‑registry.

### שיעור 6 — Git ו‑GitHub

הזרימה המלאה: `init`, `status`, `add`, `commit`, `log`, `diff`, ואז ענפים, `merge` ו‑`.gitignore`.

החלק החזק בשיעור הוא **ההשוואה בין שלושת ה‑reset**, כשכל אחד מודגם על אותו קומיט זבל:

| פקודה | הקומיט | הקובץ בדיסק | הסטטוס |
|---|---|---|---|
| `reset --soft` | בוטל | נשאר | **staged** |
| `reset --mixed` (ברירת מחדל) | בוטל | נשאר | **unstaged** |
| `reset --hard` | בוטל | **נמחק** ⚠️ | נקי |

ואז חיבור ל‑GitHub: יצירת מפתח SSH `ed25519`, `ssh-agent`, `ssh -T git@github.com`, `remote add` ו‑`push -u`. הסיום הוא תגיות — ההבדל בין תגית קלה לתגית מוערת (`-a`), והמלכודת ש‑`git push` לבדו **לא** דוחף תגיות.

### שיעור 7 — GitHub Actions

השיעור מפנה לתיקיית [`github-workflows/`](github-workflows/), שבה שבע דוגמאות בסדר עולה של מורכבות:

| קובץ | מה הוא מדגים |
|---|---|
| [`01-init.yaml`](github-workflows/01-init.yaml) | וורקפלו ראשון, `workflow_dispatch` עם inputs, ריצה בתוך container |
| [`02-seq-and-para.yaml`](github-workflows/02-seq-and-para.yaml) | jobs במקביל מול jobs בטור עם `needs` |
| [`03-matrix.yaml`](github-workflows/03-matrix.yaml) | matrix build |
| [`04-build-and-push.yaml`](github-workflows/04-build-and-push.yaml) | בנייה ודחיפה של אימג' Docker |
| [`05-pr-comment.yaml`](github-workflows/05-pr-comment.yaml) | תגובה אוטומטית על Pull Request |
| [`06-reusable-deploy.yaml`](github-workflows/06-reusable-deploy.yaml) + [`06-call-reusable-deploy.yaml`](github-workflows/06-call-reusable-deploy.yaml) | וורקפלו לשימוש חוזר והקריאה אליו |
| [`07-upload-download.yaml`](github-workflows/07-upload-download.yaml) | העלאה והורדה של artifacts |

התיקייה [`github-workflows/build-and-push/`](github-workflows/build-and-push/) מכילה את אפליקציית ה‑Python הקטנה (`app.py`, `requirements.txt`, `Dockerfile`) שהוורקפלו הרביעי בונה.

**תרגיל כיתה:** וורקפלו עם שלושה jobs — הראשון משווה תוכן קובץ למשתנה מאגר, השני משווה קובץ אחר ל‑secret, והשלישי רץ רק אם שניהם הצליחו ומדפיס את הערכים **בלי לחשוף את ה‑secret**.

### שיעור 8 — ArgoCD ו‑GitOps

מתקינים ArgoCD בקלאסטר, שולפים את סיסמת האדמין הראשונית מ‑Secret, ואז ארבעה תרגילים מדורגים בתיקיית [`argocd/`](argocd/):

1. **[`ex1/`](argocd/ex1/)** — Application ידני דרך ה‑UI שמצביע על `deployment.yaml` ו‑`svc.yaml`. משנים `replicas` בגיט ורואים את ArgoCD מסנכרן.
2. **[`ex2/mychart/`](argocd/ex2/mychart/)** — פריסת צ'ארט Helm שלם דרך ArgoCD, כולל `values-dev.yaml` ו‑`values-prod.yaml`.
3. **[`ex3/sync-wave.yaml`](argocd/ex3/sync-wave.yaml)** — Hooks ו‑Sync Waves: שליטה בסדר שבו המשאבים נוצרים.
4. **[`ex4/apps/`](argocd/ex4/apps/)** — תבנית **App of Apps**: אפליקציית `root-app` אחת שמנהלת אפליקציות ילדים, עם `finalizers` שמבטיחים מחיקה מדורגת.

**תרגיל כיתה:** לכתוב אפליקציית Kubernetes שמציגה דף HTML מותאם (ConfigMap + Service + Deployment), לפרוס אותה דרך ArgoCD, ואז **לעדכן את האתר רק דרך Git** — בלי לגעת בקלאסטר. זה בדיוק הרעיון של GitOps.

### שיעור 9 — ניטור: Prometheus ו‑Grafana

התקנת מחסנית הניטור המלאה עם Helm, לפי [`monitoring/prometheus/values.yaml`](monitoring/prometheus/values.yaml), ואז סיור בכל רכיב דרך `port-forward`:

| רכיב | פורט | תפקיד |
|---|---|---|
| Node Exporter | 9100 | מטריקות ברמת המכונה |
| Prometheus Server | 9090 | איסוף ושאילתות |
| Pushgateway | 9091 | מטריקות מ‑jobs קצרי חיים |
| Alertmanager | 9093 | ניתוב התראות |
| Grafana | 3000 | דשבורדים |

השיעור כולל **11 שאילתות PromQL** לדוגמה — מ‑`up == 1` הפשוטה, דרך חישוב אחוז CPU וזיכרון, ועד `topk`, `bottomk`, `avg_over_time` ו‑`changes`. בסוף מחברים את Grafana ל‑Prometheus כ‑data source ומייבאים דשבורדים מוכנים (`6417` ל‑kube-state-metrics, `16677` ל‑nginx ingress).

### שיעור 10 — AWS ראשוני + Terraform ראשוני

חצי ידני, חצי כקוד — וזו הנקודה:

- **ידנית בקונסולה** — הקמת EC2, התקנת Docker, הרצת NGINX, ואז הגילוי שצריך לפתוח Security Group ל‑IP שלך. בנוסף: [מחשבון העלויות](http://calculator.aws/), הקמת משתמש IAM ו‑[permissions.cloud](https://aws.permissions.cloud) לבדיקת הרשאות.
- **כקוד** — בלוק `terraform` ראשון עם `required_providers` ו‑backend מקומי, `provider "aws"`, `locals`, resource של `aws_instance` ו‑`output` של ה‑IP הציבורי.

### שיעור 11 — Terraform מתקדם

אין סקריפט לשיעור הזה, אבל תיקיית [`terraform/`](terraform/) מכילה ארבעה תרגילים שממשיכים בדיוק מאיפה ששיעור 10 נעצר:

| קובץ | מה נלמד בו |
|---|---|
| [`1.tf`](terraform/1.tf) | `variables.tf` / `outputs.tf` / `locals`, `random_string` לשמות ייחודיים, ו‑S3 bucket עם versioning — הבאקט שישמש כ‑backend בהמשך |
| [`2.tf`](terraform/2.tf) | `data` sources (VPC ו‑subnets קיימים), `count` כתנאי (`? 1 : 0`), `for_each` על map, `null_resource` עם `local-exec`, ו‑`for` expressions שמייצרים list מול map |
| [`3.tf`](terraform/3.tf) | כתיבת **מודול משלך** (`modules/ec2_with_ping/`) והפעלתו פעמיים — `dev_server` עם ping ו‑`prod_server` בלעדיו |
| [`4.tf`](terraform/4.tf) | **backend מרוחק ב‑S3** עם `use_lockfile`, שימוש במודול קהילתי (`terraform-aws-modules/vpc`), ו‑`validation` blocks — כולל כלל שאוסר סביבת prod בלי NAT gateway |

**תרגיל כיתה:** ליצור שני באקטים ב‑S3 בלולאה עם השם שלך וסיומת אקראית, להקים EC2 ו‑`null_resource` שכותב את ה‑IP הציבורי לקובץ, ולהעלות את הקובץ לשני הבאקטים.

### שיעור 12 — Serverless: Lambda, SQS ו‑DynamoDB

ארבע פונקציות Lambda בפייתון, כל אחת צעד אחד קדימה:

1. **handler בסיסי** — הדפסת ה‑`event` וה‑`environ` כדי להבין מה Lambda בכלל מקבלת
2. **Lambda + SQS** — מעבר על `event['Records']`, עיבוד ההודעה, ומחיקה מפורשת מהתור עם `receipt_handle`
3. **Lambda + Secrets Manager** — שליפת סוד עם `boto3` וטיפול נכון ב‑`ClientError`
4. **SQS ← Lambda ← DynamoDB** — הצינור המלא: קוראים JSON מהתור וכותבים ל‑DynamoDB, עם `messageId` כמפתח ראשי ואתחול ה‑resource **מחוץ** ל‑handler כדי לעשות שימוש חוזר בחיבור

### שיעור 13 — שירותי AWS מנוהלים

השיעור הכי ארוך בקורס, ובצדק:

- **CloudWatch ו‑CloudTrail** — alarms, metrics ודשבורדים, וההבדל בין event history לבין trail
- **SSM Parameter Store** — שלושת הסוגים: `String`, `StringList` (כולל קריאה ב‑boto3 ופיצול ל‑list) ו‑`SecureString` עם `--with-decryption`
- **Secrets Manager, מקצה לקצה** — יצירה, דריסה, והבנת מנגנון הגרסאות: הערך הישן שורד תחת `AWSPREVIOUS`, ואפשר לגלגל אחורה עם `update-secret-version-stage`
- **סבב סודות אוטומטי** — פונקציית Lambda שמממשת את שלבי `createSecret` ו‑`finishSecret`, חיבור ההרשאות, ו‑`rotate-secret` בתזמון של 30 יום
- **שכפול בין אזורים** — replication ל‑`eu-west-1`, וההוכחה שהעותק **קריאה בלבד**
- **מחיקה ושחזור** — כולל התקלה שכל תלמיד נופל בה: אחרי `delete-secret` השם עדיין תפוס, ו‑`create-secret` נכשל עד ש‑`restore-secret` או `--force-delete-without-recovery`
- **RDS PostgreSQL** — הקמת מסד, `CREATE DATABASE`, טבלה עם `SERIAL PRIMARY KEY`, והכנסת רשומות
- **Lambda Layers** — אריזת `psycopg2` ל‑layer עם ה‑platform וה‑ABI הנכונים, פרסום, וחיבור לפונקציה שמתחברת ל‑RDS

### שיעור 14 — Ansible

מעבדה מלאה שרצה על Docker, מ‑[`ansible-demo/docker/`](ansible-demo/docker/): קונטיינר master ושני nodes, עם `ssh-copy-id` להתחברות בלי סיסמה. אחרי ההקמה עוברים על כל היכולות:

| נושא | קובץ |
|---|---|
| Inventory ו‑config | [`config/hosts`](ansible-demo/config/hosts), [`config/ansible.cfg`](ansible-demo/config/ansible.cfg) |
| Playbook ראשון | [`playbook.yml`](ansible-demo/playbook.yml) |
| משתנים ו‑tags | [`vars.yml`](ansible-demo/vars.yml), [`vars_file.yml`](ansible-demo/vars_file.yml) |
| Handlers, register ותנאים | [`demo.yml`](ansible-demo/demo.yml) |
| Roles | [`common.yml`](ansible-demo/common.yml), [`roles/common/`](ansible-demo/roles/common/) |
| תבניות Jinja2 | [`template.yml`](ansible-demo/template.yml), [`my_hostname.j2`](ansible-demo/my_hostname.j2) |
| Ansible Galaxy | [`galaxy-role.yml`](ansible-demo/galaxy-role.yml) |
| דוגמה מלאה | [`examples/ex1/`](ansible-demo/examples/ex1/) |

לפני הכתיבה המסודרת עוברים על **פקודות Ad-Hoc** (`ansible servers -m ping`, `-m setup`, `-a "df -h"`, `-m apt`, `-m service`, `-m fetch`) — כי לפעמים לא צריך playbook בכלל.

השיעור מסתיים בשלושה נושאים מעשיים: **`ansible-vault`** להצפנת סודות ושימוש בהם דרך `--ask-vault-pass`, **`group_vars`** וההדגמה מה קורה כשמשנים את שם הקובץ (המשתנה פשוט מפסיק להיטען), ומודולים שימושיים כמו **`lineinfile`**.

---

## תרגילי Troubleshooting

תיקיית [`troubleshooting/`](troubleshooting/) היא סוג אחר של חומר — **שישה תרגילים שבורים בכוונה**. בכל אחד יש קוד שלא עובד, וצריך להריץ, לקרוא את השגיאה ולתקן:

| תרגיל | המשימה |
|---|---|
| [`00-docker/`](troubleshooting/00-docker/) | לבנות את האימג' ולוודא שהאפליקציה בפנים באמת רצה |
| [`01-github-actions/`](troubleshooting/01-github-actions/) | להריץ את `bad-action.yaml` שוב ושוב עד שהוא עובר |
| [`02-kubernetes/`](troubleshooting/02-kubernetes/) | `kubectl apply -f deploy.yaml` ולהבין למה ה‑Pods לא עולים |
| [`03-helm/`](troubleshooting/03-helm/) | `helm upgrade -i myapp ./` ולתקן את הצ'ארט |
| [`04-terraform/`](troubleshooting/04-terraform/) | `init` → `plan` → `apply` ולתקן את הקוד וה‑`tfvars` |
| [`05-ansible/`](troubleshooting/05-ansible/) | להקים את מעבדת ה‑Docker ולהריץ את `common.yml` |

## מפת התיקיות

| תיקייה | תוכן |
|---|---|
| [`scripts/`](scripts/) | יומני הפקודות של השיעורים — קובץ לכל שיעור |
| [`k8s/`](k8s/) | מניפסטים של Kubernetes, כולל `volumes/` עם 12 דוגמאות |
| [`argocd/`](argocd/) | ארבעת תרגילי ה‑GitOps + צ'ארט Helm מלא ב‑`ex2/mychart/` |
| [`github-workflows/`](github-workflows/) | 7 וורקפלואים לדוגמה + אפליקציית הדגמה לבנייה |
| [`terraform/`](terraform/) | 4 תרגילי Terraform, מ‑resource בודד עד מודולים ו‑backend מרוחק |
| [`ansible-demo/`](ansible-demo/) | מעבדת Ansible מלאה — inventory, playbooks, roles ותבניות |
| [`monitoring/`](monitoring/) | קובץ ה‑values של Prometheus לשיעור הניטור |
| [`troubleshooting/`](troubleshooting/) | 6 תרגילי איתור ותיקון תקלות |
| [`.github/workflows/`](.github/workflows/) | הוורקפלו הפעיל של הריפו עצמו |

---

## הערות

- **הריפו פרטי.** חלק מהסקריפטים מפנים לקישורי `raw.githubusercontent.com` של מאגר הקורס המקורי — הם ממשיכים לעבוד כי המאגר ההוא ציבורי. אם תעתיק אותם לכתובות של הריפו הזה הם **יישברו**, כי אי אפשר למשוך קבצים ממאגר פרטי בלי אימות.
- **הסקריפטים הם רפרנס, לא אוטומציה.** חלקם מכילים גם פלט צפוי, קטעי YAML והערות באמצע — הם נועדו לקריאה ולהעתקה שורה‑שורה, לא ל‑`bash 13.sh`.
- **מפתחות וסודות** בקבצים הם placeholders (`XXXXX`, `SuperSecret123!`) — חומר לימוד בלבד, לא להשתמש בשום מקום אמיתי.

<sub>הלוגו שייך למכללת DevOps Experts ומופיע כאן לצורכי זיהוי בלבד. הריפו הוא ארכיון לימודי אישי.</sub>

</div>
