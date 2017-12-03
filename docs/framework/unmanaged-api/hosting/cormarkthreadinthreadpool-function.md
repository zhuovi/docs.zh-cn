---
title: "CorMarkThreadInThreadPool 函数"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMarkThreadInThreadPool
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CorMarkThreadInThreadPool
helpviewer_keywords: CorMarkThreadInThreadPool function [.NET Framework hosting]
ms.assetid: 3f958d41-e82e-4ec3-ae6f-16c7b3b31e3e
topic_type: apiref
caps.latest.revision: "15"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3396bc9b3151babe5f1caf32cb2abc90f22189dc
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/18/2017
---
# <a name="cormarkthreadinthreadpool-function"></a><span data-ttu-id="d5908-102">CorMarkThreadInThreadPool 函数</span><span class="sxs-lookup"><span data-stu-id="d5908-102">CorMarkThreadInThreadPool Function</span></span>
<span data-ttu-id="d5908-103">将标记为托管代码的执行当前正在执行的线程池线程。</span><span class="sxs-lookup"><span data-stu-id="d5908-103">Marks the currently executing thread-pool thread for the execution of managed code.</span></span> <span data-ttu-id="d5908-104">从.NET Framework 2.0 版开始，此函数不起作用。</span><span class="sxs-lookup"><span data-stu-id="d5908-104">Starting with the .NET Framework version 2.0, this function has no effect.</span></span> <span data-ttu-id="d5908-105">它不是必需的并且可以在代码中删除。此函数已弃用中[!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="d5908-105">It is not required, and can be removed from your code.This function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5908-106">语法</span><span class="sxs-lookup"><span data-stu-id="d5908-106">Syntax</span></span>  
  
```  
void CorMarkThreadInThreadPool ();  
```  
  
## <a name="requirements"></a><span data-ttu-id="d5908-107">要求</span><span class="sxs-lookup"><span data-stu-id="d5908-107">Requirements</span></span>  
 <span data-ttu-id="d5908-108">**平台：**请参阅[系统要求](../../../../docs/framework/get-started/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d5908-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5908-109">**标头：** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d5908-109">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d5908-110">**库：** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d5908-110">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d5908-111">**.NET framework 版本：**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5908-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5908-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d5908-112">See Also</span></span>  
 [<span data-ttu-id="d5908-113">弃用的 CLR 承载函数</span><span class="sxs-lookup"><span data-stu-id="d5908-113">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)