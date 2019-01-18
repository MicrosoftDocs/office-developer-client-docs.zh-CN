---
title: ADO/WFC 编程
TOCTitle: ADO/WFC programming
ms:assetid: fc438cc2-00b9-9590-6e0d-a865001ccf2f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250293(v=office.15)
ms:contentKeyID: 48548887
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 904b5e3930c0e7e7b1d98f94bd39cfbf816aa145
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28720504"
---
# <a name="adowfc-programming"></a><span data-ttu-id="55b41-102">ADO/WFC 编程</span><span class="sxs-lookup"><span data-stu-id="55b41-102">ADO/WFC programming</span></span>

<span data-ttu-id="55b41-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="55b41-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="55b41-p101">对于 Microsoft Visual J++ 6.0，ADO 已经得到扩展，这使它能够按以下方式使用 Windows 基础类 (WFC)。首先，已经实现了一组 Java 类，这些类扩展了 ADO 接口，并创建了对 Java 程序员有用的通知；这些 Java 类还公开了可以将 Java 类型返回给用户的函数。为了提高性能，Java 类可以直接访问 OLE DB 行集对象中的本机数据类型，并将它们作为 Java 类型返回给 Java 程序员，而不用将它们首先转换为变量型值，或者相反。经过扩展后，ADO 还能使用 WFC 框架中的事件通知。</span><span class="sxs-lookup"><span data-stu-id="55b41-p101">For Microsoft Visual J++ 6.0, ADO has been extended to work with Windows Foundation Classes (WFC) in the following ways. First, a set of Java classes has been implemented that extends the ADO interfaces and creates notifications interesting to the Java programmer; the Java classes also expose functions that return Java types to the user. To improve performance, the Java class directly accesses the native data types in the OLE DB rowset object, and returns them to the Java programmer as Java types without first converting them to and from a variant. ADO has also been extended to work with event notifications in the WFC framework.</span></span>

<span data-ttu-id="55b41-p102">ADO for Windows Foundation Classes (ADO/WFC) 支持所有标准的 ADO 方法、属性、对象和事件。但是，那些需要变量型作为参数并且在 Microsoft Visual Basic 等语言中展示了良好性能的操作，在 Visual J++ 等语言中性能却有所降低。为此，ADO/WFC 还提供了 [Field](field-object-ado.md) 对象的访问器函数，该函数采用本机 Java 数据类型而不是变量型数据类型。</span><span class="sxs-lookup"><span data-stu-id="55b41-p102">ADO for Windows Foundation Classes (ADO/WFC) supports all the standard ADO methods, properties, objects, and events. However, operations that require a variant as a parameter and show excellent performance in a language such as Microsoft Visual Basic, display lesser performance in a language such as Visual J++. For that reason, ADO/WFC also provides accessor functions on the [Field](field-object-ado.md) object that take native Java data types instead of the variant data type.</span></span>

<span data-ttu-id="55b41-111">若要查看 ADO 文档中有关 ADO/WFC 包的更详细信息，请参阅 [ADO/WFC 语法索引](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/ado-wfc-syntax-index)。</span><span class="sxs-lookup"><span data-stu-id="55b41-111">For more detailed information within the ADO documentation about ADO/WFC packages, see [the ADO/WFC Syntax Index](https://docs.microsoft.com/office/vba/access/concepts/miscellaneous/ado-wfc-syntax-index).</span></span>

## <a name="referencing-the-library"></a><span data-ttu-id="55b41-112">引用库</span><span class="sxs-lookup"><span data-stu-id="55b41-112">Referencing the library</span></span>

<span data-ttu-id="55b41-113">若要将 ADO/WFC 数据类导入项目，请在代码中包括以下行：</span><span class="sxs-lookup"><span data-stu-id="55b41-113">To import the ADO/WFC data classes into your project, include the following line in your code:</span></span>

```java 
 
import com.ms.wfc.data.*; 
```

