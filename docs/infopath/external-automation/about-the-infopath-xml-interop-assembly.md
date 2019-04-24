---
title: 关于 InfoPath XML 互操作程序集
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
keywords:
- msxml 互操作 [infopath 2007]、infopath 2007、XML 主互操作程序集、infopath XML 互操作程序集
localization_priority: Normal
ms.assetid: fb28659b-8a71-4f43-9121-2c748fb2c5e1
description: 提供了 InfoPath XML 互操作程序集, 以允许在托管代码和由 Microsoft XML Core Services (MSXML) 从自动执行 InfoPath 的外部应用程序公开的 COM 服务器之间实现互操作性支持。
ms.openlocfilehash: 8d47fb58c5133fa14ac78aa8fb29278b70c26abb
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32303778"
---
# <a name="about-the-infopath-xml-interop-assembly"></a><span data-ttu-id="2c583-104">关于 InfoPath XML 互操作程序集</span><span class="sxs-lookup"><span data-stu-id="2c583-104">About the InfoPath XML interop assembly</span></span>

<span data-ttu-id="2c583-105">提供了 InfoPath XML 互操作程序集, 以允许在托管代码和由 Microsoft XML Core Services (MSXML) 从自动执行 InfoPath 的外部应用程序公开的 COM 服务器之间实现互操作性支持。</span><span class="sxs-lookup"><span data-stu-id="2c583-105">The InfoPath XML interop assembly is provided to allow support for interoperability between managed code and the COM server exposed by Microsoft XML Core Services (MSXML) from external applications that automate InfoPath.</span></span>

<span data-ttu-id="2c583-106">InfoPath 安装程序中的 **.net 可编程性支持**选项将安装三个互操作程序集。</span><span class="sxs-lookup"><span data-stu-id="2c583-106">The **.NET Programmability Support** option in the InfoPath setup program installs three interop assemblies.</span></span> <span data-ttu-id="2c583-107">互操作程序集是充当托管代码与非托管代码之间桥梁的 .NET 程序集，它将 COM 对象成员映射到等同的 .NET 托管成员。</span><span class="sxs-lookup"><span data-stu-id="2c583-107">Interop assemblies are .NET assemblies that act as a bridge between managed and unmanaged code, mapping COM object members to equivalent .NET managed members.</span></span> <span data-ttu-id="2c583-108">其中一个程序集 (如 ". .dll") 提供了 ". [web.xml](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.infopath.xml?view=infopath-external)命名空间" 的成员, 该命名空间用于处理由 COM server 为 Microsoft Xml Core Services (MSXML) 公开的成员。使用托管代码自动执行 InfoPath 的外部应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c583-108">One of those assemblies, Microsoft.Office.Interop.InfoPath.Xml.dll, provides the members of the [Microsoft.Office.Interop.InfoPath.Xml](https://docs.microsoft.com/dotnet/api/microsoft.office.interop.infopath.xml?view=infopath-external) namespace, which is used to work with members exposed by the COM server for Microsoft XML Core Services (MSXML) from external applications that automate InfoPath using managed code.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2c583-109">必须手动建立对 infopath external automation 项目所需的对 microsoft. .dll 和 web.xml 互操作程序集的引用, 才能对其进行引用。</span><span class="sxs-lookup"><span data-stu-id="2c583-109">The references to the Microsoft.Office.Interop.InfoPath.dll and Microsoft.Office.Interop.InfoPath.Xml.dll interop assemblies that are required for InfoPath external automation projects must be established manually.</span></span> <span data-ttu-id="2c583-110">有关外部自动化的详细信息, 请参阅[外部自动化方案和示例](external-automation-scenarios-and-examples.md)。</span><span class="sxs-lookup"><span data-stu-id="2c583-110">For more information on external automation, see [External Automation Scenarios and Examples](external-automation-scenarios-and-examples.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="2c583-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c583-111">See also</span></span>

- [<span data-ttu-id="2c583-112">使用 InfoPath 2003 对象模型处理 MSXML 和 System.Xml</span><span class="sxs-lookup"><span data-stu-id="2c583-112">Working with MSXML and System.Xml Using the InfoPath 2003 Object Model</span></span>](https://msdn.microsoft.com/library/f7a0cac5-26f9-49ed-b52c-0240ef0c9d38%28Office.15%29.aspx)

