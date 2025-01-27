```yaml
apiVersion: v1
data:
  APPSMITH_CLOUD_SERVICES_BASE_URL: https://release-cs.appsmith.com
  APPSMITH_CODEC_SIZE: "10"
  APPSMITH_DB_URL: mongodb://ydxyokoadmin:m4Vo*E0o9E@10.202.64.14:27017,10.202.64.15:27017,10.202.64.16:27017/appsmith?replicaSet=rs0&authSource=admin&ssl=false
  APPSMITH_DISABLE_IFRAME_WIDGET_SANDBOX: "false"
  APPSMITH_ENCRYPTION_PASSWORD: abcd
  APPSMITH_ENCRYPTION_SALT: abcd
  APPSMITH_FORM_LOGIN_DISABLED: "false"
  APPSMITH_MAIL_ENABLED: "false"
  APPSMITH_MAIL_HOST: https://ydx.test.apps.yokogawa.build/api/sensors/Email
  APPSMITH_MAIL_PORT: "25"
  APPSMITH_MAIL_SMTP_AUTH: "true"
  APPSMITH_MAIL_SMTP_TLS_ENABLED: "true"
  APPSMITH_OAUTH2_SAPCDC_CLIENT_ID: redZClCiq003bqsBt8aMMNM3
  APPSMITH_OAUTH2_SAPCDC_CLIENT_SECRET: MIsfNP7UTEwm0viZ4Sm98eNGnLY4JTqgrCsT6mQstStbWs9p3Li_SCKnmAiiI0szokCuBAvsksFqsDanVyUL9A
  APPSMITH_REDIS_URL: redis://appsmith-alpha-redis-master-0.appsmith-alpha-redis-headless.appsmith-alpha.svc.cluster.local:6379
  APPSMITH_SIGNUP_DISABLED: "false"
kind: ConfigMap
metadata:
  annotations:
    meta.helm.sh/release-name: appsmith-alpha
    meta.helm.sh/release-namespace: appsmith-alpha
  creationTimestamp: "2025-01-23T06:57:40Z"
  labels:
    app.kubernetes.io/instance: appsmith-alpha
    app.kubernetes.io/managed-by: Helm
    app.kubernetes.io/name: appsmith
    appsmith.sh/chart: appsmith-alpha-1.0.0
  name: appsmith-alpha
  namespace: appsmith-alpha
  resourceVersion: "214868267"
  uid: 61c4dd68-32b5-49f6-ac05-91940efa908a
```


---
## stateful set
```yaml
apiVersion: apps/v1
kind: StatefulSet
metadata:
  annotations:
    meta.helm.sh/release-name: appsmith-alpha
    meta.helm.sh/release-namespace: appsmith-alpha
  creationTimestamp: "2025-01-23T06:57:41Z"
  generation: 8
  labels:
    app.kubernetes.io/instance: appsmith-alpha
    app.kubernetes.io/managed-by: Helm
    app.kubernetes.io/name: appsmith
    appsmith.sh/chart: appsmith-alpha-1.0.0
  name: appsmith-alpha
  namespace: appsmith-alpha
  resourceVersion: "214976130"
  uid: fa1905d1-ec2d-47b6-868f-678b7cea7b86
spec:
  persistentVolumeClaimRetentionPolicy:
    whenDeleted: Retain
    whenScaled: Retain
  podManagementPolicy: OrderedReady
  replicas: 1
  revisionHistoryLimit: 10
  selector:
    matchLabels:
      app.kubernetes.io/instance: appsmith-alpha
      app.kubernetes.io/name: appsmith
  serviceName: appsmith-alpha-appsmith
  template:
    metadata:
      annotations:
        kubectl.kubernetes.io/restartedAt: "2025-01-24T09:41:42Z"
      creationTimestamp: null
      labels:
        app.kubernetes.io/instance: appsmith-alpha
        app.kubernetes.io/name: appsmith
    spec:
      affinity:
        nodeAffinity:
          requiredDuringSchedulingIgnoredDuringExecution:
            nodeSelectorTerms:
            - matchExpressions:
              - key: node
                operator: In
                values:
                - all
      containers:
      - env:
        - name: APPSMITH_ENABLE_EMBEDDED_DB
          value: "0"
        envFrom:
        - configMapRef:
            name: appsmith-alpha
        image: ydxregistry.azurecr.io/ydx/ydx-visualization-engineering-tool:896d29475cc06da03a505075970cedd177cdfd57
        imagePullPolicy: IfNotPresent
        livenessProbe:
          failureThreshold: 3
          httpGet:
            path: /api/v1/health
            port: http
            scheme: HTTP
          initialDelaySeconds: 60
          periodSeconds: 60
          successThreshold: 1
          timeoutSeconds: 1
        name: appsmith
        ports:
        - containerPort: 80
          name: http
          protocol: TCP
        - containerPort: 443
          name: https
          protocol: TCP
        readinessProbe:
          failureThreshold: 3
          httpGet:
            path: /api/v1/health
            port: http
            scheme: HTTP
          initialDelaySeconds: 60
          periodSeconds: 60
          successThreshold: 1
          timeoutSeconds: 1
        resources: {}
        startupProbe:
          failureThreshold: 3
          httpGet:
            path: /api/v1/health
            port: http
            scheme: HTTP
          initialDelaySeconds: 60
          periodSeconds: 60
          successThreshold: 1
          timeoutSeconds: 1
        terminationMessagePath: /dev/termination-log
        terminationMessagePolicy: File
        volumeMounts:
        - mountPath: /appsmith-stacks
          name: data
      dnsPolicy: ClusterFirst
      imagePullSecrets:
      - name: ydx-acr-secret
      initContainers:
      - command:
        - sh
        - -c
        - until redis-cli -h appsmith-alpha-redis-master.appsmith-alpha.svc.cluster.local
          ping; do echo waiting for redis; sleep 2; done
        image: docker.io/bitnami/redis:7.0.13-debian-11-r10
        imagePullPolicy: IfNotPresent
        name: redis-init-container
        resources: {}
        terminationMessagePath: /dev/termination-log
        terminationMessagePolicy: File
      restartPolicy: Always
      schedulerName: default-scheduler
      securityContext: {}
      serviceAccount: appsmith-alpha-appsmith
      serviceAccountName: appsmith-alpha-appsmith
      terminationGracePeriodSeconds: 30
      tolerations:
      - effect: NoSchedule
        key: node
        operator: Equal
        value: all
  updateStrategy:
    type: RollingUpdate
  volumeClaimTemplates:
  - apiVersion: v1
    kind: PersistentVolumeClaim
    metadata:
      creationTimestamp: null
      name: data
    spec:
      accessModes:
      - ReadWriteOnce
      resources:
        requests:
          storage: 10Gi
      volumeMode: Filesystem
    status:
      phase: Pending
status:
  availableReplicas: 0
  collisionCount: 0
  currentRevision: appsmith-alpha-7964989cdd
  observedGeneration: 8
  replicas: 1
  updateRevision: appsmith-alpha-85444497f8
  updatedReplicas: 1
```