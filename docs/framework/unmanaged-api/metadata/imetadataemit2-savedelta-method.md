---
title: "IMetaDataEmit2::SaveDelta 方法"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataEmit2.SaveDelta
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataEmit2::SaveDelta
helpviewer_keywords:
- IMetaDataEmit2::SaveDelta method [.NET Framework metadata]
- SaveDelta method [.NET Framework metadata]
ms.assetid: b95739fe-d2fa-4776-ae0d-31d9707ef799
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 7f2e16d994c648f3c88a23488df75f04dbdaa47a
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataemit2savedelta-method"></a><span data-ttu-id="38a01-102">IMetaDataEmit2::SaveDelta 方法</span><span class="sxs-lookup"><span data-stu-id="38a01-102">IMetaDataEmit2::SaveDelta Method</span></span>
<span data-ttu-id="38a01-103">将更改从当前的编辑并继续会话保存到指定的文件。</span><span class="sxs-lookup"><span data-stu-id="38a01-103">Saves changes from the current edit-and-continue session to the specified file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a01-104">语法</span><span class="sxs-lookup"><span data-stu-id="38a01-104">Syntax</span></span>  
  
```  
HRESULT SaveDelta (  
    [in] LPCWSTR     szFile,   
    [in] DWORD       dwSaveFlags  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="38a01-105">参数</span><span class="sxs-lookup"><span data-stu-id="38a01-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="38a01-106">[in]要保存在其下的文件名称更改。</span><span class="sxs-lookup"><span data-stu-id="38a01-106">[in] The file name under which to save changes.</span></span>  
  
 `dwSaveFlags`  
 <span data-ttu-id="38a01-107">[in]保留。</span><span class="sxs-lookup"><span data-stu-id="38a01-107">[in] Reserved.</span></span> <span data-ttu-id="38a01-108">必须为零。</span><span class="sxs-lookup"><span data-stu-id="38a01-108">Must be zero.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38a01-109">要求</span><span class="sxs-lookup"><span data-stu-id="38a01-109">Requirements</span></span>  
 <span data-ttu-id="38a01-110">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="38a01-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38a01-111">**标头：** Cor.h</span><span class="sxs-lookup"><span data-stu-id="38a01-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38a01-112">**库：**用作 MsCorEE.dll 中的资源</span><span class="sxs-lookup"><span data-stu-id="38a01-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38a01-113">**.NET framework 版本：**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38a01-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a01-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="38a01-114">See Also</span></span>  
 [<span data-ttu-id="38a01-115">IMetaDataEmit2 接口</span><span class="sxs-lookup"><span data-stu-id="38a01-115">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)  
 [<span data-ttu-id="38a01-116">IMetaDataEmit 接口</span><span class="sxs-lookup"><span data-stu-id="38a01-116">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)