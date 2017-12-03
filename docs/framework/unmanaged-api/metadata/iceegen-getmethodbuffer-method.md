---
title: "ICeeGen::GetMethodBuffer 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICeeGen.GetMethodBuffer
api_location: mscoree.dll
api_type: COM
f1_keywords: ICeeGen::GetMethodBuffer
helpviewer_keywords:
- ICeeGen::GetMethodBuffer method [.NET Framework metadata]
- GetMethodBuffer method [.NET Framework metadata]
ms.assetid: c7c5b39a-d4ac-41f1-9d1e-44163f563a49
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: be6b74de649a9b13092e6a5dcd2d2f80a215a16d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="iceegengetmethodbuffer-method"></a><span data-ttu-id="51316-102">ICeeGen::GetMethodBuffer 方法</span><span class="sxs-lookup"><span data-stu-id="51316-102">ICeeGen::GetMethodBuffer Method</span></span>
<span data-ttu-id="51316-103">获取位于指定的相对虚拟地址的方法的相应大小的缓冲区。</span><span class="sxs-lookup"><span data-stu-id="51316-103">Gets a buffer of the appropriate size for the method at the specified relative virtual address.</span></span>  
  
 <span data-ttu-id="51316-104">此方法已过时，不应使用。</span><span class="sxs-lookup"><span data-stu-id="51316-104">This method is obsolete and should not be used.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="51316-105">语法</span><span class="sxs-lookup"><span data-stu-id="51316-105">Syntax</span></span>  
  
```  
HRESULT GetMethodBuffer (  
    [in]  ULONG       RVA,  
    [out] UCHAR       **lpBuffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="51316-106">参数</span><span class="sxs-lookup"><span data-stu-id="51316-106">Parameters</span></span>  
 `RVA`  
 <span data-ttu-id="51316-107">[in]为其返回缓冲区的方法相对虚拟地址。</span><span class="sxs-lookup"><span data-stu-id="51316-107">[in] The relative virtual address of the method for which to return a buffer.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="51316-108">[out]指向返回的缓冲区的指针。</span><span class="sxs-lookup"><span data-stu-id="51316-108">[out] A pointer to the returned buffer.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="51316-109">要求</span><span class="sxs-lookup"><span data-stu-id="51316-109">Requirements</span></span>  
 <span data-ttu-id="51316-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="51316-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51316-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="51316-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="51316-112">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="51316-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="51316-113">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="51316-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51316-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="51316-114">See Also</span></span>  
 [<span data-ttu-id="51316-115">ICeeGen 接口</span><span class="sxs-lookup"><span data-stu-id="51316-115">ICeeGen Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/iceegen-interface.md)