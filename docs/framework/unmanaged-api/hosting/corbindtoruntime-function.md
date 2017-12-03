---
title: "CorBindToRuntime 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntime
api_location:
- mscoree.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CorBindToRuntime
helpviewer_keywords: CorBindToRuntime function [.NET Framework hosting]
ms.assetid: 799740aa-46ec-4532-95da-6444565b4971
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a833be39f93082e8d2c0cb28f435f754143721f2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="corbindtoruntime-function"></a><span data-ttu-id="26b1a-102">CorBindToRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="26b1a-102">CorBindToRuntime Function</span></span>
<span data-ttu-id="26b1a-103">使非托管的宿主能够将公共语言运行时 (CLR) 加载到过程中。</span><span class="sxs-lookup"><span data-stu-id="26b1a-103">Enables unmanaged hosts to load the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="26b1a-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="26b1a-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26b1a-105">语法</span><span class="sxs-lookup"><span data-stu-id="26b1a-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntime (  
    [in]  LPCWSTR     pwszVersion,   
    [in]  LPCWSTR     pwszBuildFlavor,   
    [in]  REFCLSID    rclsid,   
    [in]  REFIID      riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="26b1a-106">参数</span><span class="sxs-lookup"><span data-stu-id="26b1a-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="26b1a-107">[in]你想要加载描述的 CLR 版本的字符串。</span><span class="sxs-lookup"><span data-stu-id="26b1a-107">[in] A string describing the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="26b1a-108">.NET Framework 中的版本号用句点分隔的四个部分组成： *major.minor.build.revision*。</span><span class="sxs-lookup"><span data-stu-id="26b1a-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="26b1a-109">将字符串作为传递`pwszVersion`必须以字符"v"跟版本号 (例如，"v1.0.1529") 的前三个部分开头。</span><span class="sxs-lookup"><span data-stu-id="26b1a-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="26b1a-110">某些版本的 CLR 与指定与以前版本的 CLR 的兼容性的策略语句一起安装。</span><span class="sxs-lookup"><span data-stu-id="26b1a-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="26b1a-111">默认情况下，启动填充码将评估`pwszVersion`针对策略语句和加载运行时的最新版本的适用于所请求的版本。</span><span class="sxs-lookup"><span data-stu-id="26b1a-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="26b1a-112">主机可以强制填充码可跳过策略评估，负载中指定的确切版本`pwszVersion`通过将的值传递`STARTUP_LOADER_SAFEMODE`为`flags`参数，如下所述。</span><span class="sxs-lookup"><span data-stu-id="26b1a-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of  `STARTUP_LOADER_SAFEMODE` for the `flags` parameter, as described below.</span></span>  
  
 <span data-ttu-id="26b1a-113">如果调用方指定为 null `pwszVersion`，加载运行时的最新版本。</span><span class="sxs-lookup"><span data-stu-id="26b1a-113">If the caller specifies null for `pwszVersion`, the latest version of the runtime is loaded.</span></span> <span data-ttu-id="26b1a-114">如果传递 null 不，主机加载的运行时版本的任何控件。</span><span class="sxs-lookup"><span data-stu-id="26b1a-114">Passing null gives the host no control over which version of the runtime is loaded.</span></span> <span data-ttu-id="26b1a-115">虽然这种方法可能在某些情况下适用，但强烈建议主机提供一个要加载的特定版本。</span><span class="sxs-lookup"><span data-stu-id="26b1a-115">Although this approach may be appropriate in some scenarios, it is strongly recommended that the host supply a specific version to load.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="26b1a-116">[in]一个字符串，指定是否以加载服务器或工作站生成的 CLR。</span><span class="sxs-lookup"><span data-stu-id="26b1a-116">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="26b1a-117">有效值为 `svr` 和 `wks`。</span><span class="sxs-lookup"><span data-stu-id="26b1a-117">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="26b1a-118">服务器版本进行了优化以利用多个处理器进行垃圾回收和工作站生成优化的单处理器计算机上运行的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="26b1a-118">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="26b1a-119">如果`pwszBuildFlavor`设置为 null，则将加载工作站版本。</span><span class="sxs-lookup"><span data-stu-id="26b1a-119">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="26b1a-120">单处理器计算机上运行时，工作站生成始终处于加载状态，即使`pwszBuildFlavor`设置为`svr`。</span><span class="sxs-lookup"><span data-stu-id="26b1a-120">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="26b1a-121">但是，如果`pwszBuildFlavor`设置为`svr`和指定并发垃圾回收 (请参阅的说明`flags`参数)，则服务器将加载版本。</span><span class="sxs-lookup"><span data-stu-id="26b1a-121">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `flags` parameter), the server build is loaded.</span></span>  
  
 `rclsid`  
 <span data-ttu-id="26b1a-122">[in]`CLSID`实现的组件类的[ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)或[ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md)接口。</span><span class="sxs-lookup"><span data-stu-id="26b1a-122">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="26b1a-123">支持的值为 CLSID_CorRuntimeHost 或 CLSID_CLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="26b1a-123">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="26b1a-124">[in]`IID`从所请求的接口的`rclsid`。</span><span class="sxs-lookup"><span data-stu-id="26b1a-124">[in] The `IID` of the requested interface from `rclsid`.</span></span> <span data-ttu-id="26b1a-125">支持的值为 IID_ICorRuntimeHost 或 IID_ICLRRuntimeHost。</span><span class="sxs-lookup"><span data-stu-id="26b1a-125">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="26b1a-126">[out]指向返回的接口指针`riid`。</span><span class="sxs-lookup"><span data-stu-id="26b1a-126">[out] The returned interface pointer to `riid`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26b1a-127">备注</span><span class="sxs-lookup"><span data-stu-id="26b1a-127">Remarks</span></span>  
 <span data-ttu-id="26b1a-128">如果`pwszVersion`指定不存在，运行时版本`CorBindToRuntimeEx`返回 CLR_E_SHIM_RUNTIMELOAD HRESULT 值。</span><span class="sxs-lookup"><span data-stu-id="26b1a-128">If `pwszVersion` specifies a runtime version that does not exist, `CorBindToRuntimeEx` returns an HRESULT value of CLR_E_SHIM_RUNTIMELOAD.</span></span>  
  
## <a name="execution-context-and-flow-of-windows-identity"></a><span data-ttu-id="26b1a-129">执行上下文和的 Windows 标识的流</span><span class="sxs-lookup"><span data-stu-id="26b1a-129">Execution Context and Flow of Windows Identity</span></span>  
 <span data-ttu-id="26b1a-130">中的 clr 版本 1<xref:System.Security.Principal.WindowsIdentity>对象不流过异步点，例如新线程，线程池或计时器回调。</span><span class="sxs-lookup"><span data-stu-id="26b1a-130">In version 1 of the CLR, the <xref:System.Security.Principal.WindowsIdentity> object does not flow across asynchronous points such as new threads, thread pools, or timer callbacks.</span></span> <span data-ttu-id="26b1a-131">在 2.0 版中的 CLR，<xref:System.Threading.ExecutionContext>对象包装有关当前正在执行的线程的一些信息，并且流动它跨任何异步的点，但是不能跨应用程序域边界。</span><span class="sxs-lookup"><span data-stu-id="26b1a-131">In version 2.0 of the CLR, an <xref:System.Threading.ExecutionContext> object wraps some information about the currently executing thread and flows it across any asynchronous point, but not across application domain boundaries.</span></span> <span data-ttu-id="26b1a-132">同样，<xref:System.Security.Principal.WindowsIdentity>对象也会流过任何异步的点。</span><span class="sxs-lookup"><span data-stu-id="26b1a-132">Similarly, the <xref:System.Security.Principal.WindowsIdentity> object also flows across any asynchronous point.</span></span> <span data-ttu-id="26b1a-133">因此，当前线程上的模拟如果有的话，也会流动。</span><span class="sxs-lookup"><span data-stu-id="26b1a-133">Therefore, the current impersonation on the thread, if any, flows too.</span></span>  
  
 <span data-ttu-id="26b1a-134">您可以改变两种方式流：</span><span class="sxs-lookup"><span data-stu-id="26b1a-134">You can alter the flow in two ways:</span></span>  
  
1.  <span data-ttu-id="26b1a-135">通过修改<xref:System.Threading.ExecutionContext>设置以禁止显示的每个线程基础上的流 (请参阅<xref:System.Threading.ExecutionContext.SuppressFlow%2A>， <xref:System.Security.SecurityContext.SuppressFlow%2A>，和<xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A>方法)。</span><span class="sxs-lookup"><span data-stu-id="26b1a-135">By modifying the <xref:System.Threading.ExecutionContext> settings to suppress the flow on a per-thread basis (see the <xref:System.Threading.ExecutionContext.SuppressFlow%2A>, <xref:System.Security.SecurityContext.SuppressFlow%2A>, and <xref:System.Security.SecurityContext.SuppressFlowWindowsIdentity%2A> methods).</span></span>  
  
2.  <span data-ttu-id="26b1a-136">通过更改进程的默认模式为版本 1 兼容性模式，其中<xref:System.Security.Principal.WindowsIdentity>对象不流经任何异步的点，而不考虑<xref:System.Threading.ExecutionContext>当前线程上的设置。</span><span class="sxs-lookup"><span data-stu-id="26b1a-136">By changing the process default mode to the version 1 compatibility mode, where the <xref:System.Security.Principal.WindowsIdentity> object does not flow across any asynchronous point, regardless of the <xref:System.Threading.ExecutionContext> settings on the current thread.</span></span> <span data-ttu-id="26b1a-137">如何更改默认模式取决于是否使用托管的可执行文件或使用非托管承载接口来加载 CLR:</span><span class="sxs-lookup"><span data-stu-id="26b1a-137">How you change the default mode depends on whether you use a managed executable or an unmanaged hosting interface to load the CLR:</span></span>  
  
    1.  <span data-ttu-id="26b1a-138">用于托管可执行文件，必须设置`enabled`属性[ \<legacyImpersonationPolicy >](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md)元素`true`。</span><span class="sxs-lookup"><span data-stu-id="26b1a-138">For managed executables, you must set the `enabled` attribute of the [\<legacyImpersonationPolicy>](../../../../docs/framework/configure-apps/file-schema/runtime/legacyimpersonationpolicy-element.md) element to `true`.</span></span>  
  
    2.  <span data-ttu-id="26b1a-139">对于非托管承载接口、 将`STARTUP_LEGACY_IMPERSONATION`中标记出来`flags`参数调用时`CorBindToRuntimeEx`函数。</span><span class="sxs-lookup"><span data-stu-id="26b1a-139">For unmanaged hosting interfaces, set the `STARTUP_LEGACY_IMPERSONATION` flag in the `flags` parameter when calling the `CorBindToRuntimeEx` function.</span></span>  
  
     <span data-ttu-id="26b1a-140">版本 1 兼容模式适用于进程中的所有应用程序域和的整个过程。</span><span class="sxs-lookup"><span data-stu-id="26b1a-140">The version 1 compatibility mode applies to the entire process and to all the application domains in the process.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="26b1a-141">备注</span><span class="sxs-lookup"><span data-stu-id="26b1a-141">Remarks</span></span>  
 <span data-ttu-id="26b1a-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)和`CorBindToRuntime`执行相同的操作，但`CorBindToRuntimeEx`函数使你可以设置标志以指定的 CLR 的行为。</span><span class="sxs-lookup"><span data-stu-id="26b1a-142">[CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) and `CorBindToRuntime` perform the same operation, but the `CorBindToRuntimeEx` function allows you to set flags to specify the behavior of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="26b1a-143">要求</span><span class="sxs-lookup"><span data-stu-id="26b1a-143">Requirements</span></span>  
 <span data-ttu-id="26b1a-144">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="26b1a-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="26b1a-145">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="26b1a-145">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="26b1a-146">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="26b1a-146">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="26b1a-147">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="26b1a-147">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26b1a-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="26b1a-148">See Also</span></span>  
 [<span data-ttu-id="26b1a-149">CorBindToCurrentRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="26b1a-149">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="26b1a-150">CorBindToRuntimeByCfg 函数</span><span class="sxs-lookup"><span data-stu-id="26b1a-150">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="26b1a-151">CorBindToRuntimeEx 函数</span><span class="sxs-lookup"><span data-stu-id="26b1a-151">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="26b1a-152">CorBindToRuntimeHost 函数</span><span class="sxs-lookup"><span data-stu-id="26b1a-152">CorBindToRuntimeHost Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimehost-function.md)  
 [<span data-ttu-id="26b1a-153">ICorRuntimeHost 接口</span><span class="sxs-lookup"><span data-stu-id="26b1a-153">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="26b1a-154">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="26b1a-154">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)