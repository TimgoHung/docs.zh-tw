---
title: 架構部署方法-無伺服器應用程式
description: 不同的方式企業架構的指南會為已部署至雲端，透過 IaaS、 PaaS、 容器之間的比較和無伺服器。
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 6566971d8984ec046b8b5fa2db295c1d48c30b20
ms.sourcegitcommit: 4c158beee818c408d45a9609bfc06f209a523e22
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 07/03/2018
ms.locfileid: "49369745"
---
# <a name="architecture-deployment-approaches"></a><span data-ttu-id="968ff-103">架構的部署方法</span><span class="sxs-lookup"><span data-stu-id="968ff-103">Architecture deployment approaches</span></span>

<span data-ttu-id="968ff-104">不管架構為何方法用來設計商務應用程式，實作或部署這些應用程式可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="968ff-104">Regardless of the architecture approach used to design a business application, the implementation, or deployment of those applications may vary.</span></span> <span data-ttu-id="968ff-105">企業會裝載在實體硬體的所有項目上的應用程式，無伺服器函式。</span><span class="sxs-lookup"><span data-stu-id="968ff-105">Businesses host applications on everything from physical hardware to serverless functions.</span></span>

## <a name="n-tier-applications"></a><span data-ttu-id="968ff-106">多層式架構應用程式</span><span class="sxs-lookup"><span data-stu-id="968ff-106">N-Tier applications</span></span>

<span data-ttu-id="968ff-107">[多層式架構模式](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)是成熟的架構，而只會參考各邏輯層分成不同的實體層級的應用程式。</span><span class="sxs-lookup"><span data-stu-id="968ff-107">The [N-Tier architecture pattern](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier) is a mature architecture and simply refers to applications that separate various logical layers into separate physical tiers.</span></span> <span data-ttu-id="968ff-108">多層式架構是 N 層架構的實體實作。</span><span class="sxs-lookup"><span data-stu-id="968ff-108">N-Tier architecture is a physical implementation of N-Layer architecture.</span></span> <span data-ttu-id="968ff-109">最常見的實作，此架構包含：</span><span class="sxs-lookup"><span data-stu-id="968ff-109">The most common implementation of this architecture includes:</span></span>

* <span data-ttu-id="968ff-110">展示層中，例如 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="968ff-110">A presentation tier, for example a web app.</span></span>
* <span data-ttu-id="968ff-111">API 或資料存取層，例如 REST API。</span><span class="sxs-lookup"><span data-stu-id="968ff-111">An API or data access tier, such as a REST API.</span></span>
* <span data-ttu-id="968ff-112">資料層，例如 SQL database。</span><span class="sxs-lookup"><span data-stu-id="968ff-112">A data tier, such as a SQL database.</span></span>

![多層式架構](./media/n-tier-architecture.png)

<span data-ttu-id="968ff-114">多層式架構方案具有下列特性：</span><span class="sxs-lookup"><span data-stu-id="968ff-114">N-tier solutions have the following characteristics:</span></span>

* <span data-ttu-id="968ff-115">專案通常會配合層。</span><span class="sxs-lookup"><span data-stu-id="968ff-115">Projects are typically aligned with tiers.</span></span>
* <span data-ttu-id="968ff-116">測試可能會碰到有不同層。</span><span class="sxs-lookup"><span data-stu-id="968ff-116">Testing may be approached differently by tier.</span></span>
* <span data-ttu-id="968ff-117">層級提供的抽象層，例如展示層通常非持續性的資料層的實作詳細資料。</span><span class="sxs-lookup"><span data-stu-id="968ff-117">Tiers provide layers of abstraction, for example the presentation tier is typically ignorant of the implementation details of the data tier.</span></span>
* <span data-ttu-id="968ff-118">一般而言，層級只會與相鄰的圖層互動。</span><span class="sxs-lookup"><span data-stu-id="968ff-118">Typically, layers only interact with adjacent layers.</span></span>
* <span data-ttu-id="968ff-119">釋放通常在專案中，管理，並因此層級。</span><span class="sxs-lookup"><span data-stu-id="968ff-119">Releases are often managed at the project, and therefore tier, level.</span></span> <span data-ttu-id="968ff-120">簡單的 API 變更可能需要整個的中介層的新版本。</span><span class="sxs-lookup"><span data-stu-id="968ff-120">A simple API change may require a new release of an entire middle tier.</span></span>

<span data-ttu-id="968ff-121">此方法會提供幾項優點，包括：</span><span class="sxs-lookup"><span data-stu-id="968ff-121">This approach provides several benefits, including:</span></span>

* <span data-ttu-id="968ff-122">隔離的資料庫 （通常後端不可以直接存取資料庫後端）。</span><span class="sxs-lookup"><span data-stu-id="968ff-122">Isolation of the database (often the front end doesn't have direct access to the database back end).</span></span>
* <span data-ttu-id="968ff-123">重複使用的 api （例如，行動、 桌面和 web 應用程式用戶端可以所有重複使用相同的 Api）。</span><span class="sxs-lookup"><span data-stu-id="968ff-123">Reuse of the API (for example, mobile, desktop, and web app clients can all reuse the same APIs).</span></span>
* <span data-ttu-id="968ff-124">相應放大層彼此獨立的能力。</span><span class="sxs-lookup"><span data-stu-id="968ff-124">Ability to scale out tiers independent of each other.</span></span>
* <span data-ttu-id="968ff-125">重構隔離： 可能重構一層，而不會影響其他層。</span><span class="sxs-lookup"><span data-stu-id="968ff-125">Refactoring isolation: one tier may be refactored without impacting other tiers.</span></span>

## <a name="on-premises-and-infrastructure-as-a-service-iaas"></a><span data-ttu-id="968ff-126">在內部部署環境和基礎結構即服務 (IaaS)</span><span class="sxs-lookup"><span data-stu-id="968ff-126">On-premises and Infrastructure as a Service (IaaS)</span></span>

<span data-ttu-id="968ff-127">裝載應用程式的傳統方法需要購買硬體和管理所有軟體安裝，包括作業系統。</span><span class="sxs-lookup"><span data-stu-id="968ff-127">The traditional approach to hosting applications requires buying hardware and managing all of the software installations, including the operating system.</span></span> <span data-ttu-id="968ff-128">原本這項作業需要昂貴的資料中心與實體硬體。</span><span class="sxs-lookup"><span data-stu-id="968ff-128">Originally this involved expensive data centers and physical hardware.</span></span> <span data-ttu-id="968ff-129">隨附於作業系統的實體硬體的挑戰有很多，包括：</span><span class="sxs-lookup"><span data-stu-id="968ff-129">The challenges that come with operating physical hardware are many, including:</span></span>

* <span data-ttu-id="968ff-130">需要購買額外的 「 以防萬一 」 或尖峰需求的案例。</span><span class="sxs-lookup"><span data-stu-id="968ff-130">The need to buy excess for "just in case" or peak demand scenarios.</span></span>
* <span data-ttu-id="968ff-131">設定安全性實體存取硬體。</span><span class="sxs-lookup"><span data-stu-id="968ff-131">Securing physical access to the hardware.</span></span>
* <span data-ttu-id="968ff-132">硬體失敗 （例如磁碟錯誤） 的責任。</span><span class="sxs-lookup"><span data-stu-id="968ff-132">Responsibility for hardware failure (such as disk failure).</span></span>
* <span data-ttu-id="968ff-133">冷卻系統。</span><span class="sxs-lookup"><span data-stu-id="968ff-133">Cooling.</span></span>
* <span data-ttu-id="968ff-134">設定路由器和負載平衡器。</span><span class="sxs-lookup"><span data-stu-id="968ff-134">Configuring routers and load balancers.</span></span>
* <span data-ttu-id="968ff-135">電源備援性。</span><span class="sxs-lookup"><span data-stu-id="968ff-135">Power redundancy.</span></span>
* <span data-ttu-id="968ff-136">保護軟體的存取。</span><span class="sxs-lookup"><span data-stu-id="968ff-136">Securing software access.</span></span>

![IaaS 方法](./media/iaas-approach.png)

<span data-ttu-id="968ff-138">虛擬化硬體，透過 「 虛擬機器 」 會使基礎結構即服務 (IaaS)。</span><span class="sxs-lookup"><span data-stu-id="968ff-138">Virtualization of hardware, via "virtual machines" enables Infrastructure as a Service (IaaS).</span></span> <span data-ttu-id="968ff-139">主機電腦可以有效地分割，以提供執行個體的資源配置與他們自己的記憶體、 CPU 和儲存體。</span><span class="sxs-lookup"><span data-stu-id="968ff-139">Host machines are effectively partitioned to provide resources to instances with allocations for their own memory, CPU, and storage.</span></span> <span data-ttu-id="968ff-140">小組會佈建所需的 Vm，並設定相關聯的網路和儲存體的存取。</span><span class="sxs-lookup"><span data-stu-id="968ff-140">The team provisions the necessary VMs and configures the associated networks and access to storage.</span></span>

<span data-ttu-id="968ff-141">如需詳細資訊，請參閱 <<c0> [ 多層式架構參考架構的虛擬機器](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)。</span><span class="sxs-lookup"><span data-stu-id="968ff-141">For more information, see [virtual machine N-tier reference architecture](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier).</span></span>

<span data-ttu-id="968ff-142">雖然虛擬化和基礎結構即服務 (IaaS) 解決許多問題，它會保留大的責任的基礎結構小組手中。</span><span class="sxs-lookup"><span data-stu-id="968ff-142">Although virtualization and Infrastructure as a Service (IaaS) address many concerns, it still leaves much responsibility in the hands of the infrastructure team.</span></span> <span data-ttu-id="968ff-143">小組會維護作業系統版本、 套用安全性修補程式，並在目標電腦上安裝協力廠商相依性。</span><span class="sxs-lookup"><span data-stu-id="968ff-143">The team maintains operating system versions, applies security patches, and installs third-party dependencies on the target machines.</span></span> <span data-ttu-id="968ff-144">應用程式通常有不同的行為相較於測試環境的實際執行電腦上。</span><span class="sxs-lookup"><span data-stu-id="968ff-144">Apps often behave differently on production machines compared to the test environment.</span></span> <span data-ttu-id="968ff-145">由於不同的相依性版本和/或 OS SKU 層級，會發生問題。</span><span class="sxs-lookup"><span data-stu-id="968ff-145">Issues arise due to different dependency versions and/or OS SKU levels.</span></span> <span data-ttu-id="968ff-146">雖然許多組織部署這些目標的多層式架構應用程式，但許多公司都受益於這類部署更多的雲端原生模式[平台即服務](#platform-as-a-service-paas)。</span><span class="sxs-lookup"><span data-stu-id="968ff-146">Although many organizations deploy N-Tier applications to these targets, many companies benefit from deploying to a more cloud native model such as [Platform as a Service](#platform-as-a-service-paas).</span></span> <span data-ttu-id="968ff-147">使用微服務架構會更具有挑戰性，因為向外擴充彈性和恢復功能的需求。</span><span class="sxs-lookup"><span data-stu-id="968ff-147">Architectures with microservices are more challenging because of the requirements to scale out for elasticity and resiliency.</span></span>

<span data-ttu-id="968ff-148">如需詳細資訊，請參閱 <<c0> [ 虛擬機器](https://docs.microsoft.com/azure/virtual-machines/)。</span><span class="sxs-lookup"><span data-stu-id="968ff-148">For more information, see [virtual machines](https://docs.microsoft.com/azure/virtual-machines/).</span></span>

## <a name="platform-as-a-service-paas"></a><span data-ttu-id="968ff-149">平台即服務 (PaaS)</span><span class="sxs-lookup"><span data-stu-id="968ff-149">Platform as a Service (PaaS)</span></span>

<span data-ttu-id="968ff-150">提供服務 (PaaS) 平台設定開發人員可以直接插入的解決方案。</span><span class="sxs-lookup"><span data-stu-id="968ff-150">Platform as a Service (PaaS) offers configured solutions that developers can plug into directly.</span></span> <span data-ttu-id="968ff-151">PaaS 是另一種說法受控裝載。</span><span class="sxs-lookup"><span data-stu-id="968ff-151">PaaS is another term for managed hosting.</span></span> <span data-ttu-id="968ff-152">它就不需要管理基礎作業系統，安全性修補程式，並在許多情況下任何協力廠商相依性。</span><span class="sxs-lookup"><span data-stu-id="968ff-152">It eliminates the need to manage the base operating system, security patches and in many cases any third-party dependencies.</span></span> <span data-ttu-id="968ff-153">平台的範例包括 web 應用程式、 資料庫和行動後端。</span><span class="sxs-lookup"><span data-stu-id="968ff-153">Examples of platforms include web applications, databases, and mobile back ends.</span></span>

<span data-ttu-id="968ff-154">PaaS 解決常見 IaaS 的挑戰。</span><span class="sxs-lookup"><span data-stu-id="968ff-154">PaaS addresses the challenges common to IaaS.</span></span> <span data-ttu-id="968ff-155">PaaS 讓開發人員專注於程式碼或資料庫結構描述，而不是它取得部署的方式。</span><span class="sxs-lookup"><span data-stu-id="968ff-155">PaaS allows the developer to focus on the code or database schema rather than how it gets deployed.</span></span> <span data-ttu-id="968ff-156">PaaS 的好處包括：</span><span class="sxs-lookup"><span data-stu-id="968ff-156">Benefits of PaaS include:</span></span>

* <span data-ttu-id="968ff-157">需支付使用的模型，可排除的投資閒置機器的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="968ff-157">Pay for use models that eliminate the overhead of investing in idle machines.</span></span>
* <span data-ttu-id="968ff-158">直接部署及提升的 DevOps、 持續整合 (CI) 和持續傳遞 (CD) 管線。</span><span class="sxs-lookup"><span data-stu-id="968ff-158">Direct deployment and improved DevOps, continuous integration (CI), and continuous delivery (CD) pipelines.</span></span>
* <span data-ttu-id="968ff-159">自動升級、 更新和安全性修補程式。</span><span class="sxs-lookup"><span data-stu-id="968ff-159">Automatic upgrades, updates, and security patches.</span></span>
* <span data-ttu-id="968ff-160">按相應放大和相應增加 （彈性延展）。</span><span class="sxs-lookup"><span data-stu-id="968ff-160">Push-button scale out and scale up (elastic scale).</span></span>

<span data-ttu-id="968ff-161">PaaS 的主要缺點一直都廠商鎖定中。</span><span class="sxs-lookup"><span data-stu-id="968ff-161">The main disadvantage of PaaS traditionally has been vendor lock-in.</span></span> <span data-ttu-id="968ff-162">比方說，有些 PaaS 提供者僅支援 ASP.NET、 Node.js 或其他特定的語言及平台。</span><span class="sxs-lookup"><span data-stu-id="968ff-162">For example, some PaaS providers only support ASP.NET, Node.js, or other specific languages and platforms.</span></span> <span data-ttu-id="968ff-163">Azure App Service 等產品已演變成解決多個平台，並支援各種不同的語言和架構來裝載 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="968ff-163">Products like Azure App Service have evolved to address multiple platforms and support a variety of languages and frameworks for hosting web apps.</span></span>

![平台即服務架構](./media/paas-architecture.png)

## <a name="software-as-a-service-saas"></a><span data-ttu-id="968ff-165">軟體即服務 (SaaS)</span><span class="sxs-lookup"><span data-stu-id="968ff-165">Software as a Service (SaaS)</span></span>

<span data-ttu-id="968ff-166">軟體即服務或 SaaS 是集中託管，毋需本機安裝或佈建。</span><span class="sxs-lookup"><span data-stu-id="968ff-166">Software as a Service or SaaS is centrally hosted and available without local installation or provisioning.</span></span> <span data-ttu-id="968ff-167">SaaS 通常裝載在 PaaS 上做為部署軟體平台。</span><span class="sxs-lookup"><span data-stu-id="968ff-167">SaaS often is hosted on top of PaaS as a platform for deploying software.</span></span> <span data-ttu-id="968ff-168">SaaS 提供服務給執行並連接現有的軟體。</span><span class="sxs-lookup"><span data-stu-id="968ff-168">SaaS provides services to run and connect with existing software.</span></span> <span data-ttu-id="968ff-169">業界和垂直特定，通常是 SaaS。</span><span class="sxs-lookup"><span data-stu-id="968ff-169">SaaS is often industry and vertical specific.</span></span> <span data-ttu-id="968ff-170">SaaS 通常授權，而且通常會提供用戶端/伺服器模型。</span><span class="sxs-lookup"><span data-stu-id="968ff-170">SaaS is often licensed and typically provides a client/server model.</span></span> <span data-ttu-id="968ff-171">現今大部分的 SaaS 供應項目會用於用戶端中的 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="968ff-171">Most modern SaaS offerings use web-based apps for the client.</span></span> <span data-ttu-id="968ff-172">通常公司會將 SaaS 視為授權產品的商務解決方案中。</span><span class="sxs-lookup"><span data-stu-id="968ff-172">Companies typically consider SaaS as a business solution to license offerings.</span></span> <span data-ttu-id="968ff-173">它通常不被實作為以獲得延展性和可維護性應用程式的架構考量。</span><span class="sxs-lookup"><span data-stu-id="968ff-173">It isn't often implemented as architecture consideration for scalability and maintainability of an application.</span></span> <span data-ttu-id="968ff-174">事實上，大部分的 SaaS 解決方案是建置 IaaS、 PaaS 及/或無伺服器的後端。</span><span class="sxs-lookup"><span data-stu-id="968ff-174">Indeed, most SaaS solutions are built on IaaS, PaaS, and/or serverless back ends.</span></span>

<span data-ttu-id="968ff-175">深入了解透過 SaaS[範例應用程式](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)。</span><span class="sxs-lookup"><span data-stu-id="968ff-175">Learn more about SaaS through a [sample application](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app).</span></span>

## <a name="containers-and-functions-as-a-service-faas"></a><span data-ttu-id="968ff-176">容器和服務 」 (FaaS) 當做函式</span><span class="sxs-lookup"><span data-stu-id="968ff-176">Containers and Functions as a Service (FaaS)</span></span>

<span data-ttu-id="968ff-177">容器是有趣的解決方案，可讓 IaaS 不必類似 PaaS 的優勢。</span><span class="sxs-lookup"><span data-stu-id="968ff-177">Containers are an interesting solution that enables PaaS-like benefits without the IaaS overhead.</span></span> <span data-ttu-id="968ff-178">容器是基本上包含基本執行重複的應用程式所需的必要功能的執行階段。</span><span class="sxs-lookup"><span data-stu-id="968ff-178">A container is essentially a runtime that contains the bare essentials needed to run a unique application.</span></span> <span data-ttu-id="968ff-179">跨越主機共用核心或核心的一部分的主機作業系統和服務，例如儲存體。</span><span class="sxs-lookup"><span data-stu-id="968ff-179">The kernel or core part of the host operating system and services such as storage are shared across a host.</span></span> <span data-ttu-id="968ff-180">共用的核心，可讓 「 輕量型的容器 （有些是 mere 的大小，相較於一般的虛擬機器的 gb 大小的 mb）。</span><span class="sxs-lookup"><span data-stu-id="968ff-180">The shared kernel enables containers to be lightweight (some are mere megabytes in size, compared to the gigabyte size of typical virtual machines).</span></span> <span data-ttu-id="968ff-181">與已在執行中的主機，容器就可以啟動速度快，促進高可用性。</span><span class="sxs-lookup"><span data-stu-id="968ff-181">With hosts already running, containers can be started quickly, facilitating high availability.</span></span> <span data-ttu-id="968ff-182">能夠快速啟動容器也會提供額外的層級的復原能力。</span><span class="sxs-lookup"><span data-stu-id="968ff-182">The ability to spin up containers quickly also provides extra layers of resiliency.</span></span> <span data-ttu-id="968ff-183">Docker 是其中一個更熱門的容器實作。</span><span class="sxs-lookup"><span data-stu-id="968ff-183">Docker is one of the more popular implementations of containers.</span></span>

<span data-ttu-id="968ff-184">容器的優點包括：</span><span class="sxs-lookup"><span data-stu-id="968ff-184">Benefits of containers include:</span></span>

* <span data-ttu-id="968ff-185">輕量型和可攜式性質</span><span class="sxs-lookup"><span data-stu-id="968ff-185">Lightweight and portable</span></span>
* <span data-ttu-id="968ff-186">自封式因此不需要安裝相依性</span><span class="sxs-lookup"><span data-stu-id="968ff-186">Self-contained so no need to install dependencies</span></span>
* <span data-ttu-id="968ff-187">提供一致的環境，無論主機 （會執行在膝上型電腦上的雲端伺服器上完全相同）</span><span class="sxs-lookup"><span data-stu-id="968ff-187">Provide a consistent environment regardless of the host (runs exactly same on a laptop as on a cloud server)</span></span>
* <span data-ttu-id="968ff-188">可以向外延展快速佈建</span><span class="sxs-lookup"><span data-stu-id="968ff-188">Can be provisioned quickly for scale-out</span></span>
* <span data-ttu-id="968ff-189">您可從失敗復原快速重新啟動</span><span class="sxs-lookup"><span data-stu-id="968ff-189">Can be restarted quickly to recover from failure</span></span>

<span data-ttu-id="968ff-190">容器會執行的容器主機上 （接著可以執行裸機機器或虛擬機器上）。</span><span class="sxs-lookup"><span data-stu-id="968ff-190">A container runs on a container host (that in turn may run on a bare metal machine or a virtual machine).</span></span> <span data-ttu-id="968ff-191">多個容器或相同的容器執行個體可能會在單一主機上執行。</span><span class="sxs-lookup"><span data-stu-id="968ff-191">Multiple containers or instances of the same containers may run on a single host.</span></span> <span data-ttu-id="968ff-192">真正的容錯移轉和恢復功能，容器必須跨越主機。</span><span class="sxs-lookup"><span data-stu-id="968ff-192">For true failover and resiliency, containers must be scaled across hosts.</span></span>

<span data-ttu-id="968ff-193">如需有關 Docker 容器的詳細資訊，請參閱[什麼是 Docker](../microservices-architecture/container-docker-introduction/docker-defined.md)？</span><span class="sxs-lookup"><span data-stu-id="968ff-193">For more information about Docker containers, see [What is Docker](../microservices-architecture/container-docker-introduction/docker-defined.md)?</span></span>

<span data-ttu-id="968ff-194">管理容器主機上，通常需要 Kubernetes 等的協調流程工具。</span><span class="sxs-lookup"><span data-stu-id="968ff-194">Managing containers across hosts typically requires an orchestration tool such as Kubernetes.</span></span> <span data-ttu-id="968ff-195">設定和管理協調流程解決方案可能會加入額外的負擔與複雜性專案。</span><span class="sxs-lookup"><span data-stu-id="968ff-195">Configuring and managing orchestration solutions may add additional overhead and complexity to projects.</span></span> <span data-ttu-id="968ff-196">幸運的是，許多雲端提供者會提供透過 PaaS 解決方案，以簡化管理容器的協調流程服務。</span><span class="sxs-lookup"><span data-stu-id="968ff-196">Fortunately, many cloud providers provide orchestration services through PaaS solutions to simplify the management of containers.</span></span>

<span data-ttu-id="968ff-197">下圖顯示範例的 Kubernetes 安裝。</span><span class="sxs-lookup"><span data-stu-id="968ff-197">The following image illustrates an example Kubernetes installation.</span></span> <span data-ttu-id="968ff-198">在安裝位址向外延展和容錯移轉的節點。</span><span class="sxs-lookup"><span data-stu-id="968ff-198">Nodes in the installation address scale out and failover.</span></span> <span data-ttu-id="968ff-199">執行 Docker 容器執行個體所管理的主要伺服器。</span><span class="sxs-lookup"><span data-stu-id="968ff-199">They run Docker container instances that are managed by the master server.</span></span> <span data-ttu-id="968ff-200">*Kubelet*是轉送命令給 Docker Kubernetes 的用戶端。</span><span class="sxs-lookup"><span data-stu-id="968ff-200">The *kubelet* is the client that relays commands from Kubernetes to Docker.</span></span>

![Kubernetes](./media/kubernetes-example.png)

<span data-ttu-id="968ff-202">如需有關協調流程的詳細資訊，請參閱[在 Azure 上的 Kubernetes](https://docs.microsoft.com/azure/aks/intro-kubernetes)。</span><span class="sxs-lookup"><span data-stu-id="968ff-202">For more information about orchestration, see [Kubernetes on Azure](https://docs.microsoft.com/azure/aks/intro-kubernetes).</span></span>

<span data-ttu-id="968ff-203">為服務 」 (FaaS) 的函式是特製化的容器服務，類似於無伺服器。</span><span class="sxs-lookup"><span data-stu-id="968ff-203">Functions as a Service (FaaS) is a specialized container service that is similar to serverless.</span></span> <span data-ttu-id="968ff-204">FaaS，呼叫的特定實作[OpenFaaS](https://github.com/openfaas/faas)，位於之上提供無伺服器功能的容器。</span><span class="sxs-lookup"><span data-stu-id="968ff-204">A specific implementation of FaaS, called [OpenFaaS](https://github.com/openfaas/faas), sits on top of containers to provide serverless capabilities.</span></span> <span data-ttu-id="968ff-205">OpenFaaS 提供封裝所有執行一段程式碼所需的相依性容器的範本。</span><span class="sxs-lookup"><span data-stu-id="968ff-205">OpenFaaS provides templates that package all of the container dependencies necessary to run a piece of code.</span></span> <span data-ttu-id="968ff-206">使用範本，可簡化部署做為功能單位的程式碼的程序。</span><span class="sxs-lookup"><span data-stu-id="968ff-206">Using templates simplifies the process of deploying code as a functional unit.</span></span> <span data-ttu-id="968ff-207">OpenFaaS 的目標已包含容器和協調器，因為它可以使用現有的基礎結構的架構。</span><span class="sxs-lookup"><span data-stu-id="968ff-207">OpenFaaS targets architectures that already include containers and orchestrators because it can use the existing infrastructure.</span></span> <span data-ttu-id="968ff-208">雖然它提供無伺服器的功能，它特別需要您使用 Docker 和協調器。</span><span class="sxs-lookup"><span data-stu-id="968ff-208">Although it provides serverless functionality, it specifically requires you to use Docker and an orchestrator.</span></span>

## <a name="serverless"></a><span data-ttu-id="968ff-209">無伺服器</span><span class="sxs-lookup"><span data-stu-id="968ff-209">Serverless</span></span>

<span data-ttu-id="968ff-210">無伺服器架構提供清楚的區隔之間的程式碼，其裝載的環境。</span><span class="sxs-lookup"><span data-stu-id="968ff-210">A serverless architecture provides a clear separation between the code and its hosting environment.</span></span> <span data-ttu-id="968ff-211">實作中的程式碼*函式*藉由叫用*觸發程序*。</span><span class="sxs-lookup"><span data-stu-id="968ff-211">You implement code in a *function* that is invoked by a *trigger*.</span></span> <span data-ttu-id="968ff-212">該函式結束之後，可能會釋放它所需的資源。</span><span class="sxs-lookup"><span data-stu-id="968ff-212">After that function exits, all its needed resources may be freed.</span></span> <span data-ttu-id="968ff-213">手動、 逾時的處理程序、 HTTP 要求或檔案上傳，可能是觸發程序。</span><span class="sxs-lookup"><span data-stu-id="968ff-213">The trigger might be manual, a timed process, an HTTP request, or a file upload.</span></span> <span data-ttu-id="968ff-214">觸發程序的結果是執行的程式碼。</span><span class="sxs-lookup"><span data-stu-id="968ff-214">The result of the trigger is the execution of code.</span></span> <span data-ttu-id="968ff-215">雖然無伺服器平台而有所不同，最提供存取預先定義的 Api 和繫結，來簡化工作，例如寫入資料庫或排入佇列的結果。</span><span class="sxs-lookup"><span data-stu-id="968ff-215">Although serverless platforms vary, most provide access to pre-defined APIs and bindings to streamline tasks such as writing to a database or queueing results.</span></span>

<span data-ttu-id="968ff-216">無伺服器是高度依賴抽離主機環境，以專注於程式碼的架構。</span><span class="sxs-lookup"><span data-stu-id="968ff-216">Serverless is an architecture that relies heavily on abstracting away the host environment to focus on code.</span></span> <span data-ttu-id="968ff-217">它可以視為*較少的伺服器*。</span><span class="sxs-lookup"><span data-stu-id="968ff-217">It can be thought of as *less server*.</span></span>

<span data-ttu-id="968ff-218">容器解決方案，提供現有的開發人員建置無伺服器準備映像發佈的程式碼的指令碼。</span><span class="sxs-lookup"><span data-stu-id="968ff-218">Container solutions provide developers existing build scripts to publish code to serverless-ready images.</span></span> <span data-ttu-id="968ff-219">其他實作可將現有的 PaaS 解決方案提供可擴充的架構。</span><span class="sxs-lookup"><span data-stu-id="968ff-219">Other implementations use existing PaaS solutions to provide a scalable architecture.</span></span>

<span data-ttu-id="968ff-220">抽象概念表示，DevOps 小組不需要佈建或管理伺服器或特定的容器。</span><span class="sxs-lookup"><span data-stu-id="968ff-220">The abstraction means the DevOps team doesn't have to provision or manage servers, nor specific containers.</span></span> <span data-ttu-id="968ff-221">無伺服器平台主機程式碼，做為指令碼或封裝的可執行檔以相關的 SDK，建置，並配置的程式碼來調整所需的資源。</span><span class="sxs-lookup"><span data-stu-id="968ff-221">The serverless platform hosts code, either as script or packaged executables built with a related SDK, and allocates the necessary resources for the code to scale.</span></span>

<span data-ttu-id="968ff-222">下圖的圖表四個的無伺服器元件。</span><span class="sxs-lookup"><span data-stu-id="968ff-222">The following illustration diagrams four serverless components.</span></span> <span data-ttu-id="968ff-223">HTTP 要求會導致執行簽出 API 程式碼。</span><span class="sxs-lookup"><span data-stu-id="968ff-223">An HTTP request causes the Checkout API code to run.</span></span> <span data-ttu-id="968ff-224">簽出 API 會將程式碼插入資料庫中，並執行插入觸發程序的數個其他函式來執行工作，例如運算工作和履行的訂單。</span><span class="sxs-lookup"><span data-stu-id="968ff-224">The Checkout API inserts code into a database, and the insert triggers several other functions to run to perform tasks like computing tasks and fulfilling the order.</span></span>

![無伺服器的實作](./media/serverless-implementation.png)

<span data-ttu-id="968ff-226">無伺服器的優點包括：</span><span class="sxs-lookup"><span data-stu-id="968ff-226">The advantages of serverless include:</span></span>

* <span data-ttu-id="968ff-227">**高的密度。**</span><span class="sxs-lookup"><span data-stu-id="968ff-227">**High density.**</span></span> <span data-ttu-id="968ff-228">相較於容器或虛擬機器在相同主機上，可以執行許多相同的無伺服器程式碼的執行個體。</span><span class="sxs-lookup"><span data-stu-id="968ff-228">Many instances of the same serverless code can run on the same host compared to containers or virtual machines.</span></span> <span data-ttu-id="968ff-229">跨多個主機向外延展和恢復功能的執行個體小數位數。</span><span class="sxs-lookup"><span data-stu-id="968ff-229">The instances scale across multiple hosts scale out and resiliency.</span></span>
* <span data-ttu-id="968ff-230">**Micro 計費**。</span><span class="sxs-lookup"><span data-stu-id="968ff-230">**Micro-billing**.</span></span> <span data-ttu-id="968ff-231">根據無伺服器的執行，以便將節省大量成本在某些情況下最無伺服器的提供者帳單。</span><span class="sxs-lookup"><span data-stu-id="968ff-231">Most serverless providers bill based on serverless executions, enabling massive cost savings in certain scenarios.</span></span>
* <span data-ttu-id="968ff-232">**立即調整**。</span><span class="sxs-lookup"><span data-stu-id="968ff-232">**Instant scale**.</span></span> <span data-ttu-id="968ff-233">無伺服器可調整以符合工作負載，自動並快速。</span><span class="sxs-lookup"><span data-stu-id="968ff-233">Serverless can scale to match workloads automatically and quickly.</span></span>
* <span data-ttu-id="968ff-234">**加速上市時間，** 開發人員專注於程式碼，並將直接部署到無伺服器平台。</span><span class="sxs-lookup"><span data-stu-id="968ff-234">**Faster time to market** Developers focus on code and deploy directly to the serverless platform.</span></span> <span data-ttu-id="968ff-235">元件可以彼此釋放。</span><span class="sxs-lookup"><span data-stu-id="968ff-235">Components can be released independently of each other.</span></span>

<span data-ttu-id="968ff-236">無伺服器計算內容中最常討論，但也可以套用至資料。</span><span class="sxs-lookup"><span data-stu-id="968ff-236">Serverless is most often discussed in the context of compute, but can also apply to data.</span></span> <span data-ttu-id="968ff-237">例如， [Azure SQL](https://docs.microsoft.com/azure/sql-database)並[Cosmos DB](https://docs.microsoft.com/azure/cosmos-db)兩者都提供不需要您設定主機電腦或叢集的雲端資料庫。</span><span class="sxs-lookup"><span data-stu-id="968ff-237">For example, [Azure SQL](https://docs.microsoft.com/azure/sql-database) and [Cosmos DB](https://docs.microsoft.com/azure/cosmos-db) both provide cloud databases that don't require you to configure host machines or clusters.</span></span> <span data-ttu-id="968ff-238">這本書，著重於無伺服器計算。</span><span class="sxs-lookup"><span data-stu-id="968ff-238">This book focuses on serverless compute.</span></span>

## <a name="summary"></a><span data-ttu-id="968ff-239">總結</span><span class="sxs-lookup"><span data-stu-id="968ff-239">Summary</span></span>

<span data-ttu-id="968ff-240">沒有廣泛的架構，包括混合式方法的可用選項。</span><span class="sxs-lookup"><span data-stu-id="968ff-240">There's a broad spectrum of available choices for architecture, including a hybrid approach.</span></span> <span data-ttu-id="968ff-241">方法、 管理和成本的代價是控制項和可攜性的應用程式功能，可簡化無伺服器。</span><span class="sxs-lookup"><span data-stu-id="968ff-241">Serverless simplifies the approach, management, and cost of application features at the expense of control and portability.</span></span> <span data-ttu-id="968ff-242">不過，許多的無伺服器平台，並公開設定，以協助調整解決方案。</span><span class="sxs-lookup"><span data-stu-id="968ff-242">However, many serverless platforms do expose configuration to help fine-tune the solution.</span></span> <span data-ttu-id="968ff-243">可攜性的程式碼以及較無伺服器平台鎖定中，也可能會導致的良好程式設計作法。</span><span class="sxs-lookup"><span data-stu-id="968ff-243">Good programming practices can also lead to more portable code and less serverless platform lock-in.</span></span> <span data-ttu-id="968ff-244">下表說明的架構方法並存。</span><span class="sxs-lookup"><span data-stu-id="968ff-244">The following table illustrates the architecture approaches side by side.</span></span> <span data-ttu-id="968ff-245">選擇無伺服器根據您的擴展需求、 在您想要管理的執行階段和程度您可以讓您的工作負載分成小型的元件。</span><span class="sxs-lookup"><span data-stu-id="968ff-245">Choose serverless based on your scale needs, whether or not you want to manage the runtime, and how well you can break your workloads into small components.</span></span> <span data-ttu-id="968ff-246">您將了解潛在的挑戰，使用無伺服器和下一步 一章中的其他決策點。</span><span class="sxs-lookup"><span data-stu-id="968ff-246">You'll learn about potential challenges with serverless and other decision points in the next chapter.</span></span>

|         |<span data-ttu-id="968ff-247">IaaS</span><span class="sxs-lookup"><span data-stu-id="968ff-247">IaaS</span></span>     |<span data-ttu-id="968ff-248">PaaS</span><span class="sxs-lookup"><span data-stu-id="968ff-248">PaaS</span></span>     |<span data-ttu-id="968ff-249">容器</span><span class="sxs-lookup"><span data-stu-id="968ff-249">Container</span></span>|<span data-ttu-id="968ff-250">無伺服器</span><span class="sxs-lookup"><span data-stu-id="968ff-250">Serverless</span></span>|
|---------|---------|---------|---------|----------|
|<span data-ttu-id="968ff-251">**縮放**</span><span class="sxs-lookup"><span data-stu-id="968ff-251">**Scale**</span></span>|<span data-ttu-id="968ff-252">VM</span><span class="sxs-lookup"><span data-stu-id="968ff-252">VM</span></span>       |<span data-ttu-id="968ff-253">執行個體</span><span class="sxs-lookup"><span data-stu-id="968ff-253">Instance</span></span> |<span data-ttu-id="968ff-254">應用程式</span><span class="sxs-lookup"><span data-stu-id="968ff-254">App</span></span>      |<span data-ttu-id="968ff-255">功能</span><span class="sxs-lookup"><span data-stu-id="968ff-255">Function</span></span>  |
|<span data-ttu-id="968ff-256">**摘要**</span><span class="sxs-lookup"><span data-stu-id="968ff-256">**Abstracts**</span></span>|<span data-ttu-id="968ff-257">硬體</span><span class="sxs-lookup"><span data-stu-id="968ff-257">Hardware</span></span>|<span data-ttu-id="968ff-258">Platform</span><span class="sxs-lookup"><span data-stu-id="968ff-258">Platform</span></span>|<span data-ttu-id="968ff-259">作業系統的主機</span><span class="sxs-lookup"><span data-stu-id="968ff-259">OS Host</span></span>|<span data-ttu-id="968ff-260">執行階段</span><span class="sxs-lookup"><span data-stu-id="968ff-260">Runtime</span></span>   |
|<span data-ttu-id="968ff-261">**單位**</span><span class="sxs-lookup"><span data-stu-id="968ff-261">**Unit**</span></span> |<span data-ttu-id="968ff-262">VM</span><span class="sxs-lookup"><span data-stu-id="968ff-262">VM</span></span>       |<span data-ttu-id="968ff-263">專案</span><span class="sxs-lookup"><span data-stu-id="968ff-263">Project</span></span>  |<span data-ttu-id="968ff-264">Image</span><span class="sxs-lookup"><span data-stu-id="968ff-264">Image</span></span>    |<span data-ttu-id="968ff-265">程式碼</span><span class="sxs-lookup"><span data-stu-id="968ff-265">Code</span></span>      |
|<span data-ttu-id="968ff-266">**存留期**</span><span class="sxs-lookup"><span data-stu-id="968ff-266">**Lifetime**</span></span>|<span data-ttu-id="968ff-267">幾個月</span><span class="sxs-lookup"><span data-stu-id="968ff-267">Months</span></span>|<span data-ttu-id="968ff-268">月份的天數</span><span class="sxs-lookup"><span data-stu-id="968ff-268">Days to Months</span></span>|<span data-ttu-id="968ff-269">天前的分鐘</span><span class="sxs-lookup"><span data-stu-id="968ff-269">Minutes to Days</span></span>|<span data-ttu-id="968ff-270">分鐘的時間 （毫秒)</span><span class="sxs-lookup"><span data-stu-id="968ff-270">Milliseconds to Minutes</span></span>|
|<span data-ttu-id="968ff-271">**責任**</span><span class="sxs-lookup"><span data-stu-id="968ff-271">**Responsibility**</span></span>|<span data-ttu-id="968ff-272">應用程式、 相依性、 執行階段和作業系統</span><span class="sxs-lookup"><span data-stu-id="968ff-272">Applications, dependencies, runtime, and operating system</span></span>|<span data-ttu-id="968ff-273">應用程式和相依性</span><span class="sxs-lookup"><span data-stu-id="968ff-273">Applications and dependencies</span></span>|<span data-ttu-id="968ff-274">應用程式、 相依性，以及執行階段</span><span class="sxs-lookup"><span data-stu-id="968ff-274">Applications, dependencies, and runtime</span></span>|<span data-ttu-id="968ff-275">功能</span><span class="sxs-lookup"><span data-stu-id="968ff-275">Function</span></span>

* <span data-ttu-id="968ff-276">**擴展**指的是用來調整應用程式的單位</span><span class="sxs-lookup"><span data-stu-id="968ff-276">**Scale** refers to the unit that is used to scale the application</span></span>
* <span data-ttu-id="968ff-277">**抽象化**所實作的抽象的層級是指</span><span class="sxs-lookup"><span data-stu-id="968ff-277">**Abstracts** refers to the layer that is abstracted by the implementation</span></span>
* <span data-ttu-id="968ff-278">**單位**指的是部署的內容範圍</span><span class="sxs-lookup"><span data-stu-id="968ff-278">**Unit** refers to the scope of what is deployed</span></span>
* <span data-ttu-id="968ff-279">**存留期**指的是典型的執行階段的特定執行個體</span><span class="sxs-lookup"><span data-stu-id="968ff-279">**Lifetime** refers to the typical runtime of a specific instance</span></span>
* <span data-ttu-id="968ff-280">**責任**指的是建置、 部署及維護應用程式的額外負荷</span><span class="sxs-lookup"><span data-stu-id="968ff-280">**Responsibility** refers to the overhead to build, deploy, and maintain the application</span></span>

<span data-ttu-id="968ff-281">下一步 一章將焦點放在無伺服器架構、 使用案例和設計模式。</span><span class="sxs-lookup"><span data-stu-id="968ff-281">The next chapter will focus on serverless architecture, use cases, and design patterns.</span></span>

## <a name="recommended-resources"></a><span data-ttu-id="968ff-282">建議的資源</span><span class="sxs-lookup"><span data-stu-id="968ff-282">Recommended resources</span></span>

* [<span data-ttu-id="968ff-283">Azure 應用程式架構指南</span><span class="sxs-lookup"><span data-stu-id="968ff-283">Azure application architecture guide</span></span>](https://docs.microsoft.com/azure/architecture/guide/)
* [<span data-ttu-id="968ff-284">Azure Cosmos DB</span><span class="sxs-lookup"><span data-stu-id="968ff-284">Azure Cosmos DB</span></span>](https://docs.microsoft.com/azure/cosmos-db)
* [<span data-ttu-id="968ff-285">Azure SQL</span><span class="sxs-lookup"><span data-stu-id="968ff-285">Azure SQL</span></span>](https://docs.microsoft.com/azure/sql-database)
* [<span data-ttu-id="968ff-286">多層式架構模式</span><span class="sxs-lookup"><span data-stu-id="968ff-286">N-Tier architecture pattern</span></span>](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/n-tier)
* [<span data-ttu-id="968ff-287">在 Azure 上的 Kubernetes</span><span class="sxs-lookup"><span data-stu-id="968ff-287">Kubernetes on Azure</span></span>](https://docs.microsoft.com/azure/aks/intro-kubernetes)
* [<span data-ttu-id="968ff-288">微服務</span><span class="sxs-lookup"><span data-stu-id="968ff-288">Microservices</span></span>](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)
* [<span data-ttu-id="968ff-289">虛擬機器的多層式架構參考架構</span><span class="sxs-lookup"><span data-stu-id="968ff-289">Virtual machine N-tier reference architecture</span></span>](https://docs.microsoft.com/azure/architecture/reference-architectures/virtual-machines-windows/n-tier)
* [<span data-ttu-id="968ff-290">虛擬機器</span><span class="sxs-lookup"><span data-stu-id="968ff-290">Virtual machines</span></span>](https://docs.microsoft.com/azure/virtual-machines/)
* [<span data-ttu-id="968ff-291">什麼是 Docker？</span><span class="sxs-lookup"><span data-stu-id="968ff-291">What is Docker?</span></span>](../microservices-architecture/container-docker-introduction/docker-defined.md)
* [<span data-ttu-id="968ff-292">Wingtip Tickets SaaS 應用程式</span><span class="sxs-lookup"><span data-stu-id="968ff-292">Wingtip Tickets SaaS application</span></span>](https://docs.microsoft.com/azure/sql-database/saas-tenancy-welcome-wingtip-tickets-app)

>[!div class="step-by-step"]
<span data-ttu-id="968ff-293">[上一頁](architecture-approaches.md)
[下一頁](serverless-architecture.md)</span><span class="sxs-lookup"><span data-stu-id="968ff-293">[Previous](architecture-approaches.md)
[Next](serverless-architecture.md)</span></span>