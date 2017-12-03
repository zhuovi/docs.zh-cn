---
title: "提升和移动现有应用 Azure IaaS"
description: "更新现有的.NET 应用程序与 Azure 云和 Windows 容器。"
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 10/26/2017
ms.openlocfilehash: 7f7715bb0ec323874271a7e9ce1c666e23e33b22
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="lift-and-shift-existing-apps-azure-iaas"></a><span data-ttu-id="1c94b-103">提升和移动现有应用 Azure IaaS</span><span class="sxs-lookup"><span data-stu-id="1c94b-103">Lift and shift existing apps Azure IaaS</span></span>

> <span data-ttu-id="1c94b-104">设想： 作为第一个步骤，以降低本地投资和总成本的硬件和网络维护，只需 rehost 在云中的现有应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c94b-104">Vision: As a first step, to reduce your on-premises investment and total cost of hardware and networking maintenance, simply rehost your existing applications in the cloud.</span></span>

<span data-ttu-id="1c94b-105">在获取到之前*如何*若要迁移到 Azure 基础结构即服务 (IaaS) 平台的现有应用程序，务必分析原因*为什么*你想要迁移直接到 IaaS在 Azure 中。</span><span class="sxs-lookup"><span data-stu-id="1c94b-105">Before getting into *how* to migrate your existing applications to the Azure infrastructure as a service (IaaS) platform, it's important to analyze the reasons *why* you'd want to migrate directly to IaaS in Azure.</span></span> <span data-ttu-id="1c94b-106">在此现代化成熟度级别方案实质上是若要开始使用虚拟机在云中，而不是继续使用最新状态，本地基础结构。</span><span class="sxs-lookup"><span data-stu-id="1c94b-106">The scenario at this modernization maturity level essentially is to start using VMs in the cloud, instead of continuing to use your current, on-premises infrastructure.</span></span>

<span data-ttu-id="1c94b-107">若要分析的另一点是*为什么*可能想要迁移到纯的 IaaS 云，而不是仅仅增加了更高级的 Azure 中的托管的服务。</span><span class="sxs-lookup"><span data-stu-id="1c94b-107">Another point to analyze is *why* you might want to migrate to pure IaaS cloud instead of just adding more advanced managed services in Azure.</span></span> <span data-ttu-id="1c94b-108">你需要确定情况下可能首先需要 IaaS。</span><span class="sxs-lookup"><span data-stu-id="1c94b-108">You need to determine what cases might require IaaS in the first place.</span></span>

<span data-ttu-id="1c94b-109">图 2-1 定位现代化成熟度级别中的云基础结构的通用应用程序：</span><span class="sxs-lookup"><span data-stu-id="1c94b-109">Figure 2-1 positions Cloud Infrastructure-Ready applications in the modernization maturity levels:</span></span>

![定位云基础结构的通用应用程序](./media/image2-1.png)

> <span data-ttu-id="1c94b-111">**图 2-1。**</span><span class="sxs-lookup"><span data-stu-id="1c94b-111">**Figure 2-1.**</span></span> <span data-ttu-id="1c94b-112">定位云基础结构的通用应用程序</span><span class="sxs-lookup"><span data-stu-id="1c94b-112">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a><span data-ttu-id="1c94b-113">为什么现有.NET web 应用程序迁移到 Azure IaaS</span><span class="sxs-lookup"><span data-stu-id="1c94b-113">Why migrate existing .NET web applications to Azure IaaS</span></span> 

<span data-ttu-id="1c94b-114">若要迁移到云中，甚至在初始 IaaS 级别的主要原因是降低成本。</span><span class="sxs-lookup"><span data-stu-id="1c94b-114">The main reason to migrate to the cloud, even at an initial IaaS level, is to achieve cost reductions.</span></span> <span data-ttu-id="1c94b-115">通过使用更多的托管的基础结构服务，你的组织可能会降低其在硬件维护、 服务器或 VM 设置和部署和基础结构管理方面的投资。</span><span class="sxs-lookup"><span data-stu-id="1c94b-115">By using more managed infrastructure services, your organization can lower its investment in hardware maintenance, server or VM provisioning and deployment, and infrastructure management.</span></span>

<span data-ttu-id="1c94b-116">做出决策，以将你的应用程序移到云中后，将更熟悉为什么你可能选择 IaaS 而不是更多高级选项，如 PaaS 只需进行的 IaaS 环境的主要原因。</span><span class="sxs-lookup"><span data-stu-id="1c94b-116">After you make the decision to move your apps to the cloud, the main reason why you might choose IaaS instead of more advanced options like PaaS is simply that the IaaS environment will be more familiar.</span></span> <span data-ttu-id="1c94b-117">将移动到类似于你当前的环境，在本地环境提供较低的学习曲线，这样就最快的途径到云。</span><span class="sxs-lookup"><span data-stu-id="1c94b-117">Moving to an environment that's similar to your current, on-premises environment offers a lower learning curve, which makes it the quickest path to the cloud.</span></span>

<span data-ttu-id="1c94b-118">但是，将最快的路径发送到云中并不意味着，你会获得最大益处，无需你在云中运行的应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c94b-118">However, taking the quickest path to the cloud doesn't mean that you will gain the most benefit from having your applications running in the cloud.</span></span> <span data-ttu-id="1c94b-119">任何组织将获得从云迁移在已引入的云就绪 DevOps 和 PaaS （云进行优化） 的成熟度级别最重要的好处。</span><span class="sxs-lookup"><span data-stu-id="1c94b-119">Any organization will gain the most significant benefits from a cloud migration at the already introduced Cloud DevOps-Ready and PaaS (Cloud-Optimized) maturity levels.</span></span>

<span data-ttu-id="1c94b-120">它也具有变得非常明显应用程序是更轻松地更新和重新构建的体系结构将来时它们已在云中，即使在 IaaS 上运行。</span><span class="sxs-lookup"><span data-stu-id="1c94b-120">It also has become evident that applications are easier to modernize and re-architect in the future when they are already running in the cloud, even on IaaS.</span></span> <span data-ttu-id="1c94b-121">此 true 的部分是因为已达到应用程序数据迁移。</span><span class="sxs-lookup"><span data-stu-id="1c94b-121">This is true in part because application data migration has already been achieved.</span></span> <span data-ttu-id="1c94b-122">已此外，获得技能所需的工作在云中，并对在"云区域性"。 操作进行移位你的组织</span><span class="sxs-lookup"><span data-stu-id="1c94b-122">Also, your organization will have gained skills required for working in the cloud, and made the shift to operating in a "cloud culture."</span></span>

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a><span data-ttu-id="1c94b-123">何时将迁移到 PaaS 到而不是 IaaS</span><span class="sxs-lookup"><span data-stu-id="1c94b-123">When to migrate to IaaS instead of to PaaS</span></span>

<span data-ttu-id="1c94b-124">在下一步的部分中，我们将讨论主要基于 PaaS 平台和服务的云就绪 DevOps 应用程序。</span><span class="sxs-lookup"><span data-stu-id="1c94b-124">In the next sections, we discuss Cloud DevOps-Ready applications that are mostly based on PaaS platforms and services.</span></span> <span data-ttu-id="1c94b-125">这些应用为您提供的大多数好处迁移到云。</span><span class="sxs-lookup"><span data-stu-id="1c94b-125">These apps give you the most benefits from migrating to the cloud.</span></span>

<span data-ttu-id="1c94b-126">如果你的目标是只需将移到云的现有应用程序，首先，确定现有应用程序将需要进行大量修改，以在 Azure App Service 中运行。</span><span class="sxs-lookup"><span data-stu-id="1c94b-126">If your goal is simply to move existing applications to the cloud, first, identify existing applications that will require substantial modification to run in Azure App Service.</span></span> <span data-ttu-id="1c94b-127">这些应用程序应为第一个候选项。</span><span class="sxs-lookup"><span data-stu-id="1c94b-127">These apps should be the first candidates.</span></span>

<span data-ttu-id="1c94b-128">然后，如果你不希望或仍不能移动到 Windows 容器和/或 Azure Service Fabric 或 Kubernetes 等 orchestrators，尚未，则当你将使用纯 Vm (IaaS)。</span><span class="sxs-lookup"><span data-stu-id="1c94b-128">Then, if you don't want or still cannot move to Windows Containers and or orchestrators like Azure Service Fabric or Kubernetes, yet, then is when you would use plain VMs (IaaS).</span></span>

<span data-ttu-id="1c94b-129">但是，请记住，正确配置、 保护和维护 Vm 需要更多时间和 IT 专业人员相比于在 Azure 中使用 PaaS 服务。</span><span class="sxs-lookup"><span data-stu-id="1c94b-129">But, keep in mind that correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to using PaaS services in Azure.</span></span> <span data-ttu-id="1c94b-130">如果你正在考虑 Azure 虚拟机，请确保修补程序、 更新和管理 VM 环境所需的持续不断的维护工作将其考虑到帐户。</span><span class="sxs-lookup"><span data-stu-id="1c94b-130">If you are considering Azure Virtual Machines, make sure that you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="1c94b-131">Azure 虚拟机是 IaaS。</span><span class="sxs-lookup"><span data-stu-id="1c94b-131">Azure Virtual Machines is IaaS.</span></span>

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a><span data-ttu-id="1c94b-132">使用 Azure 迁移来分析和迁移到 Azure 的现有应用程序</span><span class="sxs-lookup"><span data-stu-id="1c94b-132">Use Azure Migrate to analyze and migrate your existing applications to Azure</span></span>

<span data-ttu-id="1c94b-133">迁移到云不一定是困难。</span><span class="sxs-lookup"><span data-stu-id="1c94b-133">Migrating to the cloud doesn't have to be difficult.</span></span> <span data-ttu-id="1c94b-134">但是，许多组织很困难，若要开始-以深入了解到的环境和应用程序、 工作负荷和数据之间紧密相互依赖关系。</span><span class="sxs-lookup"><span data-stu-id="1c94b-134">But many organizations struggle to get started - to get deep visibility into the environment and the tight interdependencies between applications, workloads, and data.</span></span> <span data-ttu-id="1c94b-135">如果该可见性，没有它可能很难计划，转发的路径。</span><span class="sxs-lookup"><span data-stu-id="1c94b-135">Without that visibility, it can be difficult to plan the path forward.</span></span> <span data-ttu-id="1c94b-136">如果没有什么已成功迁移所需的详细信息，不能在你的组织内有右对话。</span><span class="sxs-lookup"><span data-stu-id="1c94b-136">Without detailed information on what's required for a successful migration, you can't have the right conversations within your organization.</span></span> <span data-ttu-id="1c94b-137">你不知道足够有关的潜在成本效益，或工作负荷可能只需提起并移动还是需要重大改进，才能成功迁移。</span><span class="sxs-lookup"><span data-stu-id="1c94b-137">You don't know enough about the potential cost benefits, or whether workloads could just lift-and-shift or would require significant rework to migrate successfully.</span></span> <span data-ttu-id="1c94b-138">也就不足为奇对于许多组织将有所顾虑。</span><span class="sxs-lookup"><span data-stu-id="1c94b-138">No wonder many organizations hesitate.</span></span>

<span data-ttu-id="1c94b-139">[Azure 迁移](https://aka.ms/azuremigrate)是一种新的服务，提供的指导，见解和帮助您迁移到 Azure 所需的机制。</span><span class="sxs-lookup"><span data-stu-id="1c94b-139">[Azure Migrate](https://aka.ms/azuremigrate) is a new service that provides the guidance, insights, and mechanisms needed to assist you in migrating to Azure.</span></span> <span data-ttu-id="1c94b-140">Azure 迁移提供：</span><span class="sxs-lookup"><span data-stu-id="1c94b-140">Azure Migrate provides:</span></span>

-   <span data-ttu-id="1c94b-141">发现和评估的本地虚拟机</span><span class="sxs-lookup"><span data-stu-id="1c94b-141">Discovery and assessment for on-premises virtual machines</span></span>

-   <span data-ttu-id="1c94b-142">内置的依赖项的多层应用程序的高置信度发现映射</span><span class="sxs-lookup"><span data-stu-id="1c94b-142">Inbuilt dependency mapping for high-confidence discovery of multi-tier applications</span></span>

-   <span data-ttu-id="1c94b-143">智能向右大小调整到 Azure 虚拟机</span><span class="sxs-lookup"><span data-stu-id="1c94b-143">Intelligent rightsizing to Azure virtual machines</span></span>

-   <span data-ttu-id="1c94b-144">兼容性报告与修正的潜在问题的指南</span><span class="sxs-lookup"><span data-stu-id="1c94b-144">Compatibility reporting with guidelines for remediating potential issues</span></span>

-   <span data-ttu-id="1c94b-145">数据库发现和迁移与 Azure 数据库管理服务集成</span><span class="sxs-lookup"><span data-stu-id="1c94b-145">Integration with Azure Database Management Service for database discovery and migration</span></span>

<span data-ttu-id="1c94b-146">Azure 迁移可保证你的工作负荷可以迁移对业务影响最小并按预期方式在 Azure 中运行。</span><span class="sxs-lookup"><span data-stu-id="1c94b-146">Azure Migrate gives you confidence that your workloads can migrate with minimal impact to the business and run as expected in Azure.</span></span> <span data-ttu-id="1c94b-147">使用合适的工具和指南中，你可以实现最大同时确保该关键的性能的投资回报和满足可靠性需求。</span><span class="sxs-lookup"><span data-stu-id="1c94b-147">With the right tools and guidance, you can achieve maximum return on investment while assuring that critical performance and reliability needs are met.</span></span>

<span data-ttu-id="1c94b-148">图 2-2 显示了由 Azure 迁移的所有服务器和应用程序连接的内置的依赖项映射。</span><span class="sxs-lookup"><span data-stu-id="1c94b-148">Figure 2-2 shows you the built-in dependency mapping for all server and application connections performed by Azure Migrate.</span></span>

![定位云基础结构的通用应用程序](./media/image2-2.png)

> <span data-ttu-id="1c94b-150">**图 2-2。**</span><span class="sxs-lookup"><span data-stu-id="1c94b-150">**Figure 2-2.**</span></span> <span data-ttu-id="1c94b-151">定位云基础结构的通用应用程序</span><span class="sxs-lookup"><span data-stu-id="1c94b-151">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a><span data-ttu-id="1c94b-152">使用 Azure Site Recovery，以将你现有的虚拟机迁移到 Azure Vm</span><span class="sxs-lookup"><span data-stu-id="1c94b-152">Use Azure Site Recovery to migrate your existing VMs to Azure VMs</span></span>

<span data-ttu-id="1c94b-153">端到端的一部分[Azure 迁移](https://aka.ms/azuremigrate)， [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)是一个工具，可用于轻松地将你的 web 应用迁移到 Azure 中的 Vm。</span><span class="sxs-lookup"><span data-stu-id="1c94b-153">As part of the end-to-end [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) is a tool that you can use to easily migrate your web apps to VMs in Azure.</span></span> <span data-ttu-id="1c94b-154">可以使用 Site Recovery 将本地虚拟机和物理服务器复制到 Azure，或将其复制到辅助本地位置。</span><span class="sxs-lookup"><span data-stu-id="1c94b-154">You can use Site Recovery to replicate on-premises VMs and physical servers to Azure, or to replicate them to a secondary on-premises location.</span></span> <span data-ttu-id="1c94b-155">你甚至可以复制的受支持的 Azure vm，在本地上运行工作负荷*HYPER-V* VM，请在*VMware* VM，或在 Windows 或 Linux 的物理服务器上。</span><span class="sxs-lookup"><span data-stu-id="1c94b-155">You can even replicate a workload that's running on a supported Azure VM, on an on-premises *Hyper-V* VM, on a *VMware* VM, or on a Windows or Linux physical server.</span></span> <span data-ttu-id="1c94b-156">复制到 Azure 消除了的成本和维护辅助数据中心的复杂性。</span><span class="sxs-lookup"><span data-stu-id="1c94b-156">Replication to Azure eliminates the cost and complexity of maintaining a secondary datacenter.</span></span>

<span data-ttu-id="1c94b-157">专门为混合环境，部分也进行站点恢复本地和部分上的 Azure。</span><span class="sxs-lookup"><span data-stu-id="1c94b-157">Site Recovery is also made specifically for hybrid environments that are partly on-premises and partly on Azure.</span></span> <span data-ttu-id="1c94b-158">站点恢复可帮助确保业务连续性通过让你在 Vm 运行的应用和本地可用的物理服务器如果站点出现故障。</span><span class="sxs-lookup"><span data-stu-id="1c94b-158">Site Recovery helps ensure business continuity by keeping your apps that are running on VMs and on-premises physical servers available if a site goes down.</span></span> <span data-ttu-id="1c94b-159">它将复制，以便它们仍然可用在辅助位置中，如果主站点不可用的虚拟机和物理服务器运行的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="1c94b-159">It replicates workloads that are running on VMs and physical servers so that they remain available in a secondary location if the primary site isn't available.</span></span> <span data-ttu-id="1c94b-160">它将恢复到主站点时，再次运行的工作负荷。</span><span class="sxs-lookup"><span data-stu-id="1c94b-160">It recovers workloads to the primary site when it's up and running again.</span></span>

<span data-ttu-id="1c94b-161">图 2-3 说明多个 VM 迁移的执行使用 Azure Site Recovery。</span><span class="sxs-lookup"><span data-stu-id="1c94b-161">Figure 2-3 shows the execution of multiple VM migrations by using Azure Site Recovery.</span></span>

![定位云基础结构的通用应用程序](./media/image2-3.png)

> <span data-ttu-id="1c94b-163">**图 2-3。**</span><span class="sxs-lookup"><span data-stu-id="1c94b-163">**Figure 2-3.**</span></span> <span data-ttu-id="1c94b-164">定位云基础结构的通用应用程序</span><span class="sxs-lookup"><span data-stu-id="1c94b-164">Positioning Cloud Infrastructure-Ready applications</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1c94b-165">其他资源</span><span class="sxs-lookup"><span data-stu-id="1c94b-165">Additional resources</span></span>

-   <span data-ttu-id="1c94b-166">**Azure 迁移数据表**</span><span class="sxs-lookup"><span data-stu-id="1c94b-166">**Azure Migrate Datasheet**</span></span>

    [<span data-ttu-id="1c94b-167">https://aka.ms/azuremigration\_数据表</span><span class="sxs-lookup"><span data-stu-id="1c94b-167">https://aka.ms/azuremigration\_datasheet</span></span>](https://aka.ms/azuremigration\_datasheet)

-   <span data-ttu-id="1c94b-168">**Azure 迁移**</span><span class="sxs-lookup"><span data-stu-id="1c94b-168">**Azure Migrate**</span></span>

    [<span data-ttu-id="1c94b-169">http://azuremigrationcenter.com/</span><span class="sxs-lookup"><span data-stu-id="1c94b-169">http://azuremigrationcenter.com/</span></span>](http://azuremigrationcenter.com/)

-   <span data-ttu-id="1c94b-170">**将迁移到 Azure 站点恢复**</span><span class="sxs-lookup"><span data-stu-id="1c94b-170">**Migrate to Azure with Site Recovery**</span></span>

    [<span data-ttu-id="1c94b-171">https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure</span><span class="sxs-lookup"><span data-stu-id="1c94b-171">https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure</span></span>](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure)

-   <span data-ttu-id="1c94b-172">**Azure Site Recovery 服务概述**</span><span class="sxs-lookup"><span data-stu-id="1c94b-172">**Azure Site Recovery service overview**</span></span>

    [<span data-ttu-id="1c94b-173">https://docs.microsoft.com/azure/site-recovery/site-recovery-overview</span><span class="sxs-lookup"><span data-stu-id="1c94b-173">https://docs.microsoft.com/azure/site-recovery/site-recovery-overview</span></span>](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview)

-   <span data-ttu-id="1c94b-174">**在 AWS 到 Azure Vm 中的迁移 Vm**</span><span class="sxs-lookup"><span data-stu-id="1c94b-174">**Migrating VMs in AWS to Azure VMs**</span></span>

    [<span data-ttu-id="1c94b-175">https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure</span><span class="sxs-lookup"><span data-stu-id="1c94b-175">https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure</span></span>](https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure)

>[!div class="step-by-step"]
<span data-ttu-id="1c94b-176">[上一页](index.md)
[下一页](migrate-your-relational-databases-to-azure.md)</span><span class="sxs-lookup"><span data-stu-id="1c94b-176">[Previous](index.md)
[Next](migrate-your-relational-databases-to-azure.md)</span></span>