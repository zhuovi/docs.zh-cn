---
title: "序列化过程中的步骤"
ms.date: 08/07/2017
ms.prod: .net
ms.topic: article
helpviewer_keywords:
- binary serialization, steps
- serialization, steps
ms.assetid: 4bcbc883-2a91-418f-b968-6c86a25e9737
caps.latest.revision: 6
author: Erikre
ms.author: erikre
manager: erikre
ms.translationtype: HT
ms.sourcegitcommit: 717bcb6f9f72a728d77e2847096ea558a9c50902
ms.openlocfilehash: a4c125493e1b59d329bf4626c45f48b2b222d308
ms.contentlocale: zh-cn
ms.lasthandoff: 08/21/2017

---
# <a name="steps-in-the-serialization-process"></a><span data-ttu-id="97997-102">序列化过程中的步骤</span><span class="sxs-lookup"><span data-stu-id="97997-102">Steps in the serialization process</span></span>
<span data-ttu-id="97997-103">对[格式化程序](xref:System.Runtime.Serialization.Formatter)调用 <xref:System.Runtime.Serialization.Formatter.Serialize*> 方法时，将按照以下规则顺序进行对象序列化：</span><span class="sxs-lookup"><span data-stu-id="97997-103">When the <xref:System.Runtime.Serialization.Formatter.Serialize*> method is called on a [formatter](xref:System.Runtime.Serialization.Formatter), object serialization proceeds according to the following sequence of rules:</span></span>

- <span data-ttu-id="97997-104">进行检查以确定格式化程序是否具有代理项选择器。</span><span class="sxs-lookup"><span data-stu-id="97997-104">A check is made to determine whether the formatter has a surrogate selector.</span></span> <span data-ttu-id="97997-105">如果有，则检查代理项选择器是否处理给定类型的对象。</span><span class="sxs-lookup"><span data-stu-id="97997-105">If the formatter does, check whether the surrogate selector handles objects of the given type.</span></span> <span data-ttu-id="97997-106">如果选择器处理该对象类型，则在代理项选择器上调用 <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=fullName>。</span><span class="sxs-lookup"><span data-stu-id="97997-106">If the selector handles the object type, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*?displayProperty=fullName> is called on the surrogate selector.</span></span>

- <span data-ttu-id="97997-107">如果没有代理项选择器，或者代理项选择器不处理该对象类型，则进行检查以确定是否用 [Serializable](xref:System.SerializableAttribute) 属性标记了该对象。</span><span class="sxs-lookup"><span data-stu-id="97997-107">If there is no surrogate selector or if it does not handle the object type, a check is made to determine whether the object is marked with the [Serializable](xref:System.SerializableAttribute) attribute.</span></span> <span data-ttu-id="97997-108">如果未标记该对象，则会引发 <xref:System.Runtime.Serialization.SerializationException>。</span><span class="sxs-lookup"><span data-stu-id="97997-108">If the object is not, a <xref:System.Runtime.Serialization.SerializationException> is thrown.</span></span>

- <span data-ttu-id="97997-109">如果已相应地标记了对象，则检查该对象是否实现 <xref:System.Runtime.Serialization.ISerializable> 接口。</span><span class="sxs-lookup"><span data-stu-id="97997-109">If the object is marked appropriately, check whether the object implements the <xref:System.Runtime.Serialization.ISerializable> interface.</span></span> <span data-ttu-id="97997-110">如果对象实现接口，则对该对象调用 <xref:System.Runtime.Serialization.ISerializable.GetObjectData*>。</span><span class="sxs-lookup"><span data-stu-id="97997-110">If the object does, <xref:System.Runtime.Serialization.ISerializable.GetObjectData*> is called on the object.</span></span>
  
- <span data-ttu-id="97997-111">如果对象未实现 <xref:System.Runtime.Serialization.ISerializable>，则使用默认序列化策略，从而序列化所有未标记为 [NonSerialized](xref:System.NonSerializedAttribute) 的字段。</span><span class="sxs-lookup"><span data-stu-id="97997-111">If the object does not implement <xref:System.Runtime.Serialization.ISerializable>, the default serialization policy is used, serializing all fields not marked as [NonSerialized](xref:System.NonSerializedAttribute).</span></span>

[!INCLUDE [binary-serialization-warning](../../../includes/binary-serialization-warning.md)]
  
## <a name="see-also"></a><span data-ttu-id="97997-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="97997-112">See Also</span></span>  
 <span data-ttu-id="97997-113">[二进制序列化](binary-serialization.md) </span><span class="sxs-lookup"><span data-stu-id="97997-113">[Binary Serialization](binary-serialization.md) </span></span>  
 [<span data-ttu-id="97997-114">XML 和 SOAP 序列化</span><span class="sxs-lookup"><span data-stu-id="97997-114">XML and SOAP Serialization</span></span>](xml-and-soap-serialization.md)