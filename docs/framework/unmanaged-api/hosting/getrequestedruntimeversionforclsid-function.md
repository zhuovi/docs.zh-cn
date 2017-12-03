---
title: "GetRequestedRuntimeVersionForCLSID 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetRequestedRuntimeVersionForCLSID
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetRequestedRuntimeVersionForCLSID
helpviewer_keywords: GetRequestedRuntimeVersionForCLSID function [.NET Framework hosting]
ms.assetid: 5bb12f9a-0612-434b-b4ed-2db636a20bec
topic_type: apiref
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 4a5b9e4b186b6c9b91c1182e8700268f0e1c038f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="getrequestedruntimeversionforclsid-function"></a><span data-ttu-id="22abb-102">GetRequestedRuntimeVersionForCLSID 函数</span><span class="sxs-lookup"><span data-stu-id="22abb-102">GetRequestedRuntimeVersionForCLSID Function</span></span>
<span data-ttu-id="22abb-103">获取适当的公共语言运行时 (CLR) 版本信息，使用指定的类`CLSID`。</span><span class="sxs-lookup"><span data-stu-id="22abb-103">Gets the appropriate common language runtime (CLR) version information for the class with the specified `CLSID`.</span></span>  
  
 <span data-ttu-id="22abb-104">此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="22abb-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="22abb-105">语法</span><span class="sxs-lookup"><span data-stu-id="22abb-105">Syntax</span></span>  
  
```  
HRESULT GetRequestedRuntimeVersionForCLSID (  
    [in]  REFCLSID   rclsid,   
    [out]  LPWSTR     pVersion,   
    [in]  DWORD      cchBuffer,   
    [out] DWORD*     dwLength,   
    [in]  CLSID_RESOLUTION_FLAGS dwResolutionFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="22abb-106">参数</span><span class="sxs-lookup"><span data-stu-id="22abb-106">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="22abb-107">[in] `CLSID`的组件。</span><span class="sxs-lookup"><span data-stu-id="22abb-107">[in]  The `CLSID` of the component.</span></span>  
  
 `pVersion`  
 <span data-ttu-id="22abb-108">[out] 包含成功完成后的版本号字符串的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="22abb-108">[out]  A buffer that contains the version number string upon successful completion.</span></span>  
  
 `cchBuffer`  
 <span data-ttu-id="22abb-109">[in] 大小，以宽字符为单位的`pVersion`缓冲区。</span><span class="sxs-lookup"><span data-stu-id="22abb-109">[in]  The size, in wide characters, of the `pVersion` buffer.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="22abb-110">[out]返回的缓冲区长度 （字节）。</span><span class="sxs-lookup"><span data-stu-id="22abb-110">[out] The length, in bytes, of the returned buffer.</span></span>  
  
 `dwResolutionFlags`  
 <span data-ttu-id="22abb-111">[in] CLSID_RESOLUTION_FLAGS 值之一。</span><span class="sxs-lookup"><span data-stu-id="22abb-111">[in]  One of the CLSID_RESOLUTION_FLAGS values.</span></span> <span data-ttu-id="22abb-112">支持以下值：</span><span class="sxs-lookup"><span data-stu-id="22abb-112">The following values are supported:</span></span>  
  
-   <span data-ttu-id="22abb-113">CLSID_RESOLUTION_DEFAULT: (0x0) 该默认互操作行为指定应使用。</span><span class="sxs-lookup"><span data-stu-id="22abb-113">CLSID_RESOLUTION_DEFAULT: (0x0) Specifies that default interop behavior should be used.</span></span>  
  
-   <span data-ttu-id="22abb-114">CLSID_RESOLUTION_REGISTERED: (0x1) 指定注册表应搜索并填充策略应为应用。</span><span class="sxs-lookup"><span data-stu-id="22abb-114">CLSID_RESOLUTION_REGISTERED: (0x1) Specifies that the registry should be searched and shim policy should be applied.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="22abb-115">返回值</span><span class="sxs-lookup"><span data-stu-id="22abb-115">Return Value</span></span>  
  
|<span data-ttu-id="22abb-116">HRESULT</span><span class="sxs-lookup"><span data-stu-id="22abb-116">HRESULT</span></span>|<span data-ttu-id="22abb-117">描述</span><span class="sxs-lookup"><span data-stu-id="22abb-117">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="22abb-118">S_OK</span><span class="sxs-lookup"><span data-stu-id="22abb-118">S_OK</span></span>|<span data-ttu-id="22abb-119">该函数成功返回。</span><span class="sxs-lookup"><span data-stu-id="22abb-119">The function returned successfully.</span></span>|  
|<span data-ttu-id="22abb-120">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="22abb-120">E_INVALIDARG</span></span>|<span data-ttu-id="22abb-121">其中一个参数具有无效的类型或格式。</span><span class="sxs-lookup"><span data-stu-id="22abb-121">One of the parameters has an invalid type or format.</span></span>|  
|<span data-ttu-id="22abb-122">ERROR_INSUFFICIENT_BUFFER</span><span class="sxs-lookup"><span data-stu-id="22abb-122">ERROR_INSUFFICIENT_BUFFER</span></span>|<span data-ttu-id="22abb-123">`pVersion`的缓冲区不可足以容纳完整版本字符串。</span><span class="sxs-lookup"><span data-stu-id="22abb-123">The `pVersion` buffer is not large enough to hold the entire version string.</span></span>|  
|<span data-ttu-id="22abb-124">REGDB_E_CLASSNOTREG</span><span class="sxs-lookup"><span data-stu-id="22abb-124">REGDB_E_CLASSNOTREG</span></span>|<span data-ttu-id="22abb-125">没有注册使用指定的类`CLSID`。</span><span class="sxs-lookup"><span data-stu-id="22abb-125">There is no class registered with the specified `CLSID`.</span></span>|  
|<span data-ttu-id="22abb-126">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="22abb-126">E_POINTER</span></span>|<span data-ttu-id="22abb-127">`dwLength`为 null，或`cchBuffer`足够大，能够容纳的版本字符串，但`pVersion`为 null。</span><span class="sxs-lookup"><span data-stu-id="22abb-127">`dwLength` is null, or `cchBuffer` is large enough to hold the version string, but `pVersion` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="22abb-128">要求</span><span class="sxs-lookup"><span data-stu-id="22abb-128">Requirements</span></span>  
 <span data-ttu-id="22abb-129">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="22abb-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="22abb-130">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="22abb-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="22abb-131">**.NET framework 版本：**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="22abb-131">**.NET Framework Versions:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22abb-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="22abb-132">See Also</span></span>  
 [<span data-ttu-id="22abb-133">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="22abb-133">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)