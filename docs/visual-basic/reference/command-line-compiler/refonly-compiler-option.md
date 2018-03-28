---
title: -refonly (Visual Basic)
ms.date: 03/16/2018
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- -refonly
helpviewer_keywords:
- /refonly compiler option [Visual Basic]
- -refonly compiler option [Visual Basic]
- refonly compiler option [Visual Basic]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f5135ef4d33ddde27416e48c28425aa5b029237b
ms.sourcegitcommit: c883637b41ee028786edceece4fa872939d2e64c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2018
---
# <a name="-refonly-visual-basic"></a><span data-ttu-id="705ee-102">-refonly (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="705ee-102">-refonly (Visual Basic)</span></span>

<span data-ttu-id="705ee-103">**-Refonly**选项指示编译的主输出应引用程序集而不是实现程序集。</span><span class="sxs-lookup"><span data-stu-id="705ee-103">The **-refonly** option indicates that the primary output of the compilation should be a reference assembly instead of an implementation assembly.</span></span> <span data-ttu-id="705ee-104">`-refonly` 参数以无提示方式禁用输出 PDB，因为无法执行引用程序集。</span><span class="sxs-lookup"><span data-stu-id="705ee-104">The `-refonly` parameter silently disables outputting PDBs, as reference assemblies cannot be executed.</span></span>

[!INCLUDE[compiler-options](~/includes/compiler-options.md)]

## <a name="syntax"></a><span data-ttu-id="705ee-105">语法</span><span class="sxs-lookup"><span data-stu-id="705ee-105">Syntax</span></span>

```console
-refonly
```

## <a name="remarks"></a><span data-ttu-id="705ee-106">备注</span><span class="sxs-lookup"><span data-stu-id="705ee-106">Remarks</span></span>

<span data-ttu-id="705ee-107">Visual Basic 支持`-refout`切换从版本 15.3 开始。</span><span class="sxs-lookup"><span data-stu-id="705ee-107">Visual Basic supports the `-refout` switch starting with version 15.3.</span></span>

<span data-ttu-id="705ee-108">引用程序集是包含元数据，但没有实现代码的仅包含元数据的程序集。</span><span class="sxs-lookup"><span data-stu-id="705ee-108">Reference assemblies are metadata-only assemblies that contain metadata but no implementation code.</span></span> <span data-ttu-id="705ee-109">它们包括用于匿名类型以外的所有内容的类型和成员信息。</span><span class="sxs-lookup"><span data-stu-id="705ee-109">They include type and member information for everything except anonymous types.</span></span> <span data-ttu-id="705ee-110">使用 `throw null` 主体（而非不使用主体）的原因在于，这样做可以运行和传递 PEVerify（从而验证元数据的完整性）。</span><span class="sxs-lookup"><span data-stu-id="705ee-110">The reason for using `throw null` bodies (as opposed to no bodies) is so that PEVerify could run and pass (thus validating the completeness of the metadata).</span></span>

<span data-ttu-id="705ee-111">引用程序集包括程序集级别[ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute)属性。</span><span class="sxs-lookup"><span data-stu-id="705ee-111">Reference assemblies include an assembly-level [ReferenceAssembly](xref:System.Runtime.CompilerServices.ReferenceAssemblyAttribute) attribute.</span></span> <span data-ttu-id="705ee-112">可以在源中指定此属性（之后编译器就不需要进行合成）。</span><span class="sxs-lookup"><span data-stu-id="705ee-112">This attribute may be specified in source (then the compiler won't need to synthesize it).</span></span> <span data-ttu-id="705ee-113">由于此属性，运行时将无法加载执行的引用程序集 （但仍可以在仅限反射上下文中加载它们）。</span><span class="sxs-lookup"><span data-stu-id="705ee-113">Because of this attribute, runtimes will refuse to load reference assemblies for execution (but they can still be loaded in a reflection-only context).</span></span> <span data-ttu-id="705ee-114">在程序集反映的工具需要确保它们的加载为仅限反射的; 的引用程序集否则，运行时会引发<xref:System.BadImageFormatException>。</span><span class="sxs-lookup"><span data-stu-id="705ee-114">Tools that reflect on assemblies need to ensure they load reference assemblies as reflection-only; otherwise, the runtime throws a <xref:System.BadImageFormatException>.</span></span>

<span data-ttu-id="705ee-115">`-refonly` 和 [`-refout`](refout-compiler-option.md) 选项互斥。</span><span class="sxs-lookup"><span data-stu-id="705ee-115">The `-refonly` and [`-refout`](refout-compiler-option.md) options are mutually exclusive.</span></span>

## <a name="see-also"></a><span data-ttu-id="705ee-116">请参阅</span><span class="sxs-lookup"><span data-stu-id="705ee-116">See also</span></span>
<span data-ttu-id="705ee-117">[-refout](refout-compiler-option.md) </span><span class="sxs-lookup"><span data-stu-id="705ee-117">[-refout](refout-compiler-option.md) </span></span>  
[<span data-ttu-id="705ee-118">Visual Basic 命令行编译器</span><span class="sxs-lookup"><span data-stu-id="705ee-118">Visual Basic Command-Line Compiler</span></span>](index.md)  
[<span data-ttu-id="705ee-119">示例编译命令行</span><span class="sxs-lookup"><span data-stu-id="705ee-119">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)   