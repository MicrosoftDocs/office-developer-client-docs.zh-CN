---
title: 有关 InfoPath XML 互操作程序集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- msxml 互操作 [infopath 2007]，InfoPath 2007，XML 主互操作程序集、 InfoPath XML 互操作程序集
localization_priority: Normal
ms.assetid: fb28659b-8a71-4f43-9121-2c748fb2c5e1
description: InfoPath XML 互操作程序集提供允许托管的代码和由 Microsoft XML Core Services (MSXML) 公开来自外部应用程序的自动执行 InfoPath COM 服务器之间的互操作性支持。
ms.openlocfilehash: 8d3fb1c1de141fe23c655e82b77d83a8e2b11abd
ms.sourcegitcommit: 9d60cd82b5413446e5bc8ace2cd689f683fb41a7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/11/2018
ms.locfileid: "19773860"
---
# <a name="about-the-infopath-xml-interop-assembly"></a><span data-ttu-id="06805-104">有关 InfoPath XML 互操作程序集</span><span class="sxs-lookup"><span data-stu-id="06805-104">About the InfoPath XML interop assembly</span></span>

<span data-ttu-id="06805-105">InfoPath XML 互操作程序集提供允许托管的代码和由 Microsoft XML Core Services (MSXML) 公开来自外部应用程序的自动执行 InfoPath COM 服务器之间的互操作性支持。</span><span class="sxs-lookup"><span data-stu-id="06805-105">The InfoPath XML interop assembly is provided to allow support for interoperability between managed code and the COM server exposed by Microsoft XML Core Services (MSXML) from external applications that automate InfoPath.</span></span>

<span data-ttu-id="06805-106">InfoPath 安装程序中的 **.NET 可编程性支持**选项安装三个互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="06805-106">The **.NET Programmability Support** option in the InfoPath setup program installs three interop assemblies.</span></span> <span data-ttu-id="06805-107">互操作程序集是充当托管代码与非托管代码之间桥梁的 .NET 程序集，它将 COM 对象成员映射到等同的 .NET 托管成员。</span><span class="sxs-lookup"><span data-stu-id="06805-107">Interop assemblies are .NET assemblies that act as a bridge between managed and unmanaged code, mapping COM object members to equivalent .NET managed members.</span></span> <span data-ttu-id="06805-108">这些程序集，Microsoft.Office.Interop.InfoPath.Xml.dll，之一提供用于处理由 COM 服务器公开 Microsoft XML Core Services (MSXML) 的成员的[Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/en-us/library/microsoft.office.interop.infopath.xml)命名空间的成员从外部应用程序的自动执行 InfoPath 托管的代码使用。</span><span class="sxs-lookup"><span data-stu-id="06805-108">One of those assemblies, Microsoft.Office.Interop.InfoPath.Xml.dll, provides the members of the [Microsoft.Office.Interop.InfoPath.Xml](https://msdn.microsoft.com/en-us/library/microsoft.office.interop.infopath.xml) namespace, which is used to work with members exposed by the COM server for Microsoft XML Core Services (MSXML) from external applications that automate InfoPath using managed code.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="06805-109">必须手动建立对 Microsoft.Office.Interop.InfoPath.dll 和 Microsoft.Office.Interop.InfoPath.Xml.dll 互操作程序集所需的 InfoPath 外部自动化项目的引用。</span><span class="sxs-lookup"><span data-stu-id="06805-109">The references to the Microsoft.Office.Interop.InfoPath.dll and Microsoft.Office.Interop.InfoPath.Xml.dll interop assemblies that are required for InfoPath external automation projects must be established manually.</span></span> <span data-ttu-id="06805-110">外部自动化的详细信息，请参阅[外部自动化方案和示例](external-automation-scenarios-and-examples.md)。</span><span class="sxs-lookup"><span data-stu-id="06805-110">For more information on external automation, see [External Automation Scenarios and Examples](external-automation-scenarios-and-examples.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="06805-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="06805-111">See also</span></span>

- [<span data-ttu-id="06805-112">使用 InfoPath 2003 对象模型处理 MSXML 和 System.Xml</span><span class="sxs-lookup"><span data-stu-id="06805-112">Working with MSXML and System.Xml Using the InfoPath 2003 Object Model</span></span>](http://msdn.microsoft.com/library/f7a0cac5-26f9-49ed-b52c-0240ef0c9d38%28Office.15%29.aspx)

