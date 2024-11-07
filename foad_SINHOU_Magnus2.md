1) Composants sélectionnés :
- Amazon ECS avec Fargate : Permet le déployement de mes images Docker (backend et frontend) sans gestion de serveurs.
- Elastic Load Balancer (ELB) : Permet de répartit le trafic entre mos instances ECS sur deux zones de disponibilité, garantissant haute disponibilité et redondance.
- Amazon RDS (Aurora Serverless) : Permet de stocker des données persistantes dans une base de données relationnelle gérée.
- Amazon S3 : Héberge des fichiers statiques de l’application (si besoin).
- Amazon CloudFront : Fournit un CDN pour distribuer efficacement du contenu statique.
- Amazon Route 53 : Assure la gestion DNS et le routage vers votre application, y compris la redondance multi-zone.
- CloudWatch et X-Ray : Permettent la surveillance des performances et la journalisation.
- IAM : Gère l'accès sécurisé aux différents services


2) ![Exemple de schéma AWS](hetic-infra-2\Diagramme sans nom.drawio (1).png)

3) 
- Amazon Elastic Container Service (ECS) avec Fargate
Justification : ECS Fargate permet de déployer et gérer des conteneurs Docker sans avoir à gérer les serveurs sous-jacents. Fargate est serverless, ce qui répond bien aux exigences d'une architecture managée et élastique, capable de s'adapter aux pics de charge sans intervention manuelle.
- AWS Elastic Load Balancer (ELB)
Justification : Le Load Balancer permet de distribuer le trafic entrant vers les différentes instances ECS réparties dans plusieurs zones de disponibilité, garantissant ainsi une haute disponibilité et une redondance multi-zone.
- Amazon RDS (ou Aurora Serverless)
Justification : Pour une base de données managée, sécurisée, et scalable, Amazon RDS est idéal pour héberger des données structurées. Aurora Serverless peut également être un bon choix si l’application doit s’adapter automatiquement à des variations de charges, ce qui est souvent le cas pour une architecture en microservices.
- Amazon S3 (pour le stockage de fichiers statiques)
Justification : S3 est un service de stockage durable et scalable, idéal pour héberger des fichiers statiques (comme des images, vidéos, ou fichiers de configuration) qui peuvent être nécessaires à l'application.
- Amazon CloudFront (CDN)
Justification : En utilisant CloudFront, il est possible de distribuer les ressources statiques de manière rapide et sécurisée à travers le monde, avec une faible latence. Cela améliore l’expérience utilisateur, surtout si l'application doit être accessible de manière internationale.
- Amazon Route 53
Justification : Route 53 offre une gestion DNS fiable et une haute disponibilité pour acheminer les utilisateurs vers l'application de manière efficace. En combinaison avec CloudFront et le Load Balancer, cela garantit une architecture robuste et redondante.
- Amazon CloudWatch et AWS X-Ray (pour la surveillance et le suivi)
Justification : Ces services permettent de surveiller l’application en temps réel et de détecter des anomalies. CloudWatch capture les métriques et logs tandis que X-Ray aide à diagnostiquer et optimiser les performances des requêtes via un suivi distribué.
- Amazon IAM (Identity and Access Management)
Justification : IAM garantit un contrôle d'accès sécurisé aux différents services et ressources AWS, ce qui est essentiel pour une application conforme aux bonnes pratiques de sécurité.

4) 
ECR (Elastic Container Registry) : Stocke et fournit les images Docker backend et frontend à ECS Fargate.