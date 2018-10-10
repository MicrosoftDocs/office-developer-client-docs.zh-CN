---
title: Visual C++ Extensions for ADO
TOCTitle: Visual C++ Extensions for ADO
ms:assetid: 38048ae0-1dae-9e5e-c569-04011df8b5aa
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249134(v=office.15)
ms:contentKeyID: 48544212
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: f7d3a5e876dd98e26c2eb9169a21a8dcd5e532e2
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467776"
---
# <a name="visual-c-extensions-for-ado"></a><span data-ttu-id="db07d-102">Visual C++ Extensions for ADO</span><span class="sxs-lookup"><span data-stu-id="db07d-102">Visual C++ Extensions for ADO</span></span>


<span data-ttu-id="db07d-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="db07d-103">**Applies to**: Access 2013 | Office 2013</span></span>

<span data-ttu-id="db07d-104">Visual c + + ADO 编程的首选的方法使用**\#导入**指令，如下所述在[Microsoft Visual c + + ADO 编程](visual-c-ado-programming.md)。</span><span class="sxs-lookup"><span data-stu-id="db07d-104">The preferred method of programming ADO with Visual C++ is using the **\#import** directive, as discussed in [Microsoft Visual C++ ADO Programming](visual-c-ado-programming.md).</span></span> <span data-ttu-id="db07d-105">但是，更早的 ADO 版本为使用 Visual C++ 编程提供了替代方法：Visual C++ Extensions。</span><span class="sxs-lookup"><span data-stu-id="db07d-105">However, earlier versions of ADO shipped with an alternate method of programming using Visual C++: the Visual C++ Extensions.</span></span> <span data-ttu-id="db07d-106">本节介绍此功能的那些必须维护 Visual c + + Extensions 代码，但应通过编写新的 ADO 代码\#**导入**。</span><span class="sxs-lookup"><span data-stu-id="db07d-106">This section documents this feature for those who must maintain Visual C++ Extensions code, but new ADO code should be written using \#**import**.</span></span>

<span data-ttu-id="db07d-p102">Visual C++ 程序员在用 ADO 检索数据时所面对的一项最繁琐的工作是将作为 VARIANT 数据类型返回的数据转换成 C++ 数据类型，然后将经过转换的数据存储在类或结构中。除了麻烦外，通过 VARIANT 数据类型来检索 C++ 数据会使性能降低。</span><span class="sxs-lookup"><span data-stu-id="db07d-p102">One of the most tedious jobs Visual C++ programmers face when retrieving data with ADO is converting data returned as a VARIANT data type into a C++ data type, and then storing the converted data in a class or structure. In addition to being cumbersome, retrieving C++ data through a VARIANT data type diminishes performance.</span></span>

<span data-ttu-id="db07d-p103">ADO 提供的接口可以支持将数据检索为本机 C/C++ 数据类型，而不需要通过 VARIANT，并且还提供了预处理器宏来简化接口的使用。因此，该灵活工具更容易使用，并且有很好的性能。</span><span class="sxs-lookup"><span data-stu-id="db07d-p103">ADO provides an interface that supports retrieving data into native C/C++ data types without going through a VARIANT, and also provides preprocessor macros that simplify using the interface. The result is a flexible tool that is easier to use and has great performance.</span></span>

<span data-ttu-id="db07d-p104">常见的 C/C++ 客户端方案是将 [Recordset](recordset-object-ado.md) 中的记录绑定到包含本机 C/C++ 类型的 C/C++ 结构或类。通过 VARIANT 实现时，这涉及编写从 VARIANT 到 C/C++ 本机类型的转换代码。Visual C++ Extensions for ADO 的目标是使 Visual C++ 程序员更方便地使用此方案。</span><span class="sxs-lookup"><span data-stu-id="db07d-p104">A common C/C++ client scenario is to bind a record in a [Recordset](recordset-object-ado.md) to a C/C++ struct or class containing native C/C++ types. When going through VARIANTs, this involves writing conversion code from VARIANT to C/C++ native types. The Visual C++ Extensions for ADO are targeted at making this scenario much easier for the Visual C++ programmer.</span></span>

<span data-ttu-id="db07d-114">若要了解有关 Visual C++ Extensions for ADO 的详细信息，请参阅以下主题。</span><span class="sxs-lookup"><span data-stu-id="db07d-114">See the following topics to learn more about the Visual C++ Extensions for ADO.</span></span>

  - [<span data-ttu-id="db07d-115">使用 Visual C++ Extensions for ADO</span><span class="sxs-lookup"><span data-stu-id="db07d-115">Using Visual C++ Extensions for ADO</span></span>](using-visual-c-extensions.md)

  - [<span data-ttu-id="db07d-116">Visual C++ Extensions 头</span><span class="sxs-lookup"><span data-stu-id="db07d-116">Visual C++ Extensions Header</span></span>](visual-c-extensions-header.md)

  - [<span data-ttu-id="db07d-117">在 Visual C++ Extensions 中使用 ADO 的示例</span><span class="sxs-lookup"><span data-stu-id="db07d-117">ADO with Visual C++ Extensions Example</span></span>](visual-c-extensions-example.md)

