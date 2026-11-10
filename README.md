<!-- GitHub 조직 소개 README와 같은 내용이다. 그림과 저장소 링크는 절대 주소로 둔다. -->
<div align="center">

<img src="https://raw.githubusercontent.com/Softbank-Hackathon-Team/.github/main/profile/assets/banner.svg" alt="KROSS · Zero Trust Migration · Cross Boundaries. Never Trust Blindly." width="100%">

**Team Iron**

아무것도 내주지 않고, 출발 환경 그대로 어디로든.

돌고 있는 서비스를 공통 명세 하나로 읽고, 고객에게 **키도, 포트도, DB도** 열어 달라고 하지 않은 채<br>
**AWS · GCP · 온프레미스** 사이를 서비스 중단 없이 옮기는 **멀티 클라우드 이전 플랫폼**

</div>

> **SoftBank Hackathon 2026 in Korea · 본선 · Team Iron**<br>
> 소스는 팀 저장소 [Softbank-Hackathon-Team/Service](https://github.com/Softbank-Hackathon-Team/Service)이고, 이 레포에는 `service/` 서브모듈로 들어 있습니다.

## 🔩 Team Iron

Team Iron의 플랫폼 **KROSS**는 새 인프라에 앱을 처음부터 다시 올리는 도구가 아닙니다. **이미 운영 중인 서비스**를 관찰 역할로 읽어 공통 명세(IR)로 바꾸고, 환경 어댑터가 도착지의 Terraform·Helm으로 번역한 뒤, DB 논리 복제와 트래픽 가중치 전환으로 **멈추지 않고** 옮깁니다. 모든 실행은 사람이 승인한 계획 지문대로만 움직이고, 실패하면 출발로 되돌립니다.

> **Connect → Import & IR → Plan & Approve → Provision → Deploy (GitOps) → Replicate → Shift 10·50·100% → Cutover → Cleanup**

<p align="center"><img src="https://raw.githubusercontent.com/Softbank-Hackathon-Team/.github/main/profile/assets/flow.png" alt="읽고, 번역하고, 옮긴다" width="100%"></p>

## 🛡️ 이전하는 동안의 보안, 다섯 겹

1. **입구에 열린 포트 없음** · Cloudflare 터널이 플랫폼 안에서 밖으로 열린다
2. **권한을 한 파드에 가둠** · API 서버는 클라우드 권한 0, 고객 권한은 전용 노드의 워커 하나만
3. **고객 키 0** · AWS STS 15분 임시 역할, GCP WIF + 회사별 서비스 계정
4. **AI는 권한 0** · 결과물은 일회용 vCluster 리허설 뒤 사람이 승인해야 나간다
5. **데이터·배포 길도 닫힌 채로** · 온프레는 GitOps를 안에서 당겨 가 들어오는 포트 0, 온프레로 가는 DB는 일회용 중계기로만 복제

## 📊 실측

| | |
|---|---|
| ⏱️ **20분** | AWS → 온프레 실이전 완료, 컷오버 쓰기 멈춤 약 120ms (1회 측정) |
| 🔒 **0회** | GCP → 온프레 실이전 감사 로그에서 플랫폼이 받은 역할 밖 권한을 쓴 횟수 |
| 🔀 **10 → 50 → 100%** | 공개 입구 실요청이 온프레로 단계 전환, 롤백 시 자원 자동 정리 |

## 🛠️ Tech Stack

### ⚙️ Platform

![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?style=for-the-badge&logo=typescript&logoColor=white) ![Node.js](https://img.shields.io/badge/Node.js-339933?style=for-the-badge&logo=nodedotjs&logoColor=white) ![Fastify](https://img.shields.io/badge/Fastify-000000?style=for-the-badge&logo=fastify&logoColor=white) ![Zod](https://img.shields.io/badge/Zod-3E67B1?style=for-the-badge&logo=zod&logoColor=white) ![PostgreSQL](https://img.shields.io/badge/PostgreSQL_·_pg--boss-4169E1?style=for-the-badge&logo=postgresql&logoColor=white) ![React](https://img.shields.io/badge/React-61DAFB?style=for-the-badge&logo=react&logoColor=black)

### ☁️ Clouds & Infrastructure

![AWS](https://img.shields.io/badge/AWS-232F3E?style=for-the-badge&logo=amazonwebservices&logoColor=white) ![Google Cloud](https://img.shields.io/badge/Google_Cloud-4285F4?style=for-the-badge&logo=googlecloud&logoColor=white) ![k3s](https://img.shields.io/badge/k3s_On--Prem-FFC61C?style=for-the-badge&logo=k3s&logoColor=black) ![Terraform](https://img.shields.io/badge/Terraform-844FBA?style=for-the-badge&logo=terraform&logoColor=white) ![Kubernetes](https://img.shields.io/badge/Kubernetes-326CE5?style=for-the-badge&logo=kubernetes&logoColor=white) ![CloudNativePG](https://img.shields.io/badge/CloudNativePG-336791?style=for-the-badge&logo=postgresql&logoColor=white)

### 🔁 Delivery & Traffic

![Argo CD](https://img.shields.io/badge/Argo_CD-EF7B4D?style=for-the-badge&logo=argo&logoColor=white) ![Helm](https://img.shields.io/badge/Helm-0F1689?style=for-the-badge&logo=helm&logoColor=white) ![Cloudflare](https://img.shields.io/badge/Cloudflare_LB_·_Tunnel-F38020?style=for-the-badge&logo=cloudflare&logoColor=white) ![GitHub Actions](https://img.shields.io/badge/GitHub_Actions-2088FF?style=for-the-badge&logo=githubactions&logoColor=white)

### 🛡️ Security & Sandbox

![External Secrets](https://img.shields.io/badge/External_Secrets-5A4FCF?style=for-the-badge&logo=kubernetes&logoColor=white) ![Sealed Secrets](https://img.shields.io/badge/Sealed_Secrets-2F855A?style=for-the-badge&logo=kubernetes&logoColor=white) ![vCluster](https://img.shields.io/badge/vCluster_·_gVisor-0F172A?style=for-the-badge&logo=kubernetes&logoColor=white) ![Kyverno](https://img.shields.io/badge/Kyverno-FF6F00?style=for-the-badge&logo=kubernetes&logoColor=white)

### 📈 Observability & AI

![OpenTelemetry](https://img.shields.io/badge/OpenTelemetry-000000?style=for-the-badge&logo=opentelemetry&logoColor=white) ![Prometheus](https://img.shields.io/badge/Prometheus-E6522C?style=for-the-badge&logo=prometheus&logoColor=white) ![Grafana](https://img.shields.io/badge/Grafana-F46800?style=for-the-badge&logo=grafana&logoColor=white) ![Anthropic Claude](https://img.shields.io/badge/Anthropic_Claude-191919?style=for-the-badge&logo=anthropic&logoColor=white)

## 🏗️ Architecture

<p align="center"><img src="https://raw.githubusercontent.com/Softbank-Hackathon-Team/.github/main/profile/assets/architecture-v0.6.png" alt="본선 아키텍처 v0.6" width="100%"></p>

## 🚀 Migration Flow

1. 고객 환경 연결 (링크·스크립트로 임시 역할만, 키 0개)
2. 돌고 있는 서비스 가져오기 → 공통 명세(IR), 사람이 확인
3. 사전 점검 → 이전 계획 → 비용 고지 → 계획 지문 승인
4. 환경 어댑터가 Terraform 입력·Helm 값으로 번역, 도착 자원 생성
5. 배포 전 리허설(일회용 vCluster) → GitOps 커밋 → Argo CD 동기화
6. DB 논리 복제 (일회용 중계기, 복제 지연 확인)
7. Cloudflare LB 가중치 10 → 50 → 100% 단계 전환, 지표가 나쁘면 출발로 롤백 (결선 시연은 판정 지표를 고정값으로 돌림)
8. 컷오버 → 롤백 가능 창 → 중계기·임시 권한 정리

## 📦 Repositories

| 레포 | 설명 |
|---|---|
| [**Service**](https://github.com/Softbank-Hackathon-Team/Service) | 이전 플랫폼 본체: 콘솔 · API · 워커 · 어댑터 · 인프라 모듈 |
| **gitops** (비공개) | 승인된 계획을 고객 클러스터로 내보내는 배포 레포 (Argo CD app-of-apps) |

## 👥 팀 구성원

Team Iron · 5명

<table>
  <tr>
    <th align="center">이정</th>
    <th align="center">박승준</th>
    <th align="center">오채건</th>
    <th align="center">박소정</th>
    <th align="center">강윤주</th>
  </tr>
  <tr>
    <td align="center">Team Lead<br>Architecture · Control Plane</td>
    <td align="center">Sandbox Rehearsal<br>Cloud Provisioning · Web Console</td>
    <td align="center">Security · Governance<br>On-premises</td>
    <td align="center">Platform Infra<br>Traffic · Observability</td>
    <td align="center">Platform Infra<br>Terraform · EKS</td>
  </tr>
  <tr>
    <td align="center"><a href="https://github.com/Pionia5375">@Pionia5375</a></td>
    <td align="center"><a href="https://github.com/Seungjun1127">@Seungjun1127</a></td>
    <td align="center"><a href="https://github.com/fl0wizy">@fl0wizy</a></td>
    <td align="center"><a href="https://github.com/sojjeoi">@sojjeoi</a></td>
    <td align="center"><a href="https://github.com/yunjuka">@yunjuka</a></td>
  </tr>
</table>

역할 상세는 [Service README의 Team Iron](https://github.com/Softbank-Hackathon-Team/Service#-team-iron)을 따릅니다.

---

<div align="center"><b>Team Iron · SoftBank Hackathon 2026</b><br>이정 · 박승준 · 오채건 · 박소정 · 강윤주</div>
