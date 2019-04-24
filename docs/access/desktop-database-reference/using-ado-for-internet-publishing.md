---
title: 使用 ADO for Internet Publishing
TOCTitle: Using ADO for Internet Publishing
ms:assetid: 1e829783-fc12-e303-6f12-2df1ca96cb0f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ248975(v=office.15)
ms:contentKeyID: 48543622
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: ae8341151c7bf7d90585794061647ba33a5c4ea7
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32305899"
---
# <a name="using-ado-for-internet-publishing"></a><span data-ttu-id="6cc1b-102">使用 ADO 进行 Internet 发布</span><span class="sxs-lookup"><span data-stu-id="6cc1b-102">Using ADO for Internet publishing</span></span>


<span data-ttu-id="6cc1b-103">**适用于**：Access 2013、Office 2013</span><span class="sxs-lookup"><span data-stu-id="6cc1b-103">**Applies to**: Access 2013, Office 2013</span></span>



<span data-ttu-id="6cc1b-104">[OLE DB Provider for Internet Publishing](the-ole-db-provider-for-internet-publishing.md) 中显示了一个用 ADO 访问异类数据的具体示例。</span><span class="sxs-lookup"><span data-stu-id="6cc1b-104">[The OLE DB Provider for Internet Publishing](the-ole-db-provider-for-internet-publishing.md) shows a specific example of accessing heterogeneous data with ADO.</span></span> <span data-ttu-id="6cc1b-105">虽然本节中的示例特定于使用 Internet 发布提供程序, 但在将 ADO 与其他提供程序与异类数据 (如提供程序到电子邮件存储) 结合使用时, 演示的原则应类似于。</span><span class="sxs-lookup"><span data-stu-id="6cc1b-105">While the examples in this section will be specific to using the Internet Publishing Provider, the principles demonstrated should be similar when using ADO with other providers to heterogeneous data, such as a provider to an email store.</span></span>

## <a name="urls"></a><span data-ttu-id="6cc1b-106">URL</span><span class="sxs-lookup"><span data-stu-id="6cc1b-106">URLs</span></span>

<span data-ttu-id="6cc1b-p102">统一资源定位器 (URL) 可作为连接字符串和命令文本的替代，用于指定数据源和文件与目录位置。您可以将 URL 用于现有的 [Connection](connection-object-ado.md) 和 **Recordset** 对象以及 **Record** 和 **Stream** 对象。</span><span class="sxs-lookup"><span data-stu-id="6cc1b-p102">Uniform Resource Locators (URLs) can be used as an alternative to connection strings and command text to specify data sources and the location of files and directories. You can use URLs with the existing [Connection](connection-object-ado.md) and **Recordset** objects as well as with the **Record** and **Stream** objects.</span></span>

<span data-ttu-id="6cc1b-109">有关使用 URL 的详细信息，请参阅[绝对 URL 和相对 URL](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="6cc1b-109">For more information about using URLs, see [Absolute and Relative URLs](absolute-and-relative-urls.md).</span></span>

## <a name="record-fields"></a><span data-ttu-id="6cc1b-110">记录字段</span><span class="sxs-lookup"><span data-stu-id="6cc1b-110">Record Fields</span></span>

<span data-ttu-id="6cc1b-p103">异类数据与同类数据之间的差别在于，前者的每个数据行或**记录**都有不同的列集或**字段**。而后者的每个数据行具有相同的列集。有关特定于 Internet Publishing Provider 的字段的详细信息，请参阅[记录和提供程序提供的字段](records-and-provider-supplied-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="6cc1b-p103">The distinguishing difference between heterogeneous data and homogeneous data is that for the former, each row of data, or **Record**, can have a different set of columns, or **Fields**. For homogeneous data, each row has the same set of columns. For more information about the fields specific to the Internet Publishing Provider, see [Records and Provider-Supplied Fields](records-and-provider-supplied-fields.md).</span></span>

## <a name="appending-new-fields"></a><span data-ttu-id="6cc1b-114">追加新字段</span><span class="sxs-lookup"><span data-stu-id="6cc1b-114">Appending New Fields</span></span>

<span data-ttu-id="6cc1b-115">以下是几个新增的 ADO 对象，可以与 **Record** 和 **Stream** 对象一起使用。</span><span class="sxs-lookup"><span data-stu-id="6cc1b-115">Several ADO objects have been enhanced to work in conjunction with **Record** and **Stream** objects.</span></span>

  - <span data-ttu-id="6cc1b-116">[Fields](fields-collection-ado.md) 集合的 [Append](append-method-ado.md) 方法，用于在集合中创建和添加 [Field](field-object-ado.md) 对象，还可用于指定 **Field** 的值。</span><span class="sxs-lookup"><span data-stu-id="6cc1b-116">The [Fields](fields-collection-ado.md) collection [Append](append-method-ado.md) method, which creates and adds a [Field](field-object-ado.md) object to the collection, can also specify the value of the **Field**.</span></span>

  - <span data-ttu-id="6cc1b-117">[Update](update-method-ado.md) 方法，用于完成集合中字段的添加和删除。</span><span class="sxs-lookup"><span data-stu-id="6cc1b-117">The [Update](update-method-ado.md) method finalizes the addition or deletion of fields to the collection.</span></span>

  - <span data-ttu-id="6cc1b-118">您可以通过简单地为未定义字段或以前删除的字段赋值来创建字段，以作为 **Append** 方法的快捷方式和替代方式。</span><span class="sxs-lookup"><span data-stu-id="6cc1b-118">As a shortcut and alternative to the **Append** method, you may create fields by simply assigning a value to an undefined or previously deleted field.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cc1b-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cc1b-119">See also</span></span>

- [<span data-ttu-id="6cc1b-120">Internet 发布方案主题</span><span class="sxs-lookup"><span data-stu-id="6cc1b-120">Internet Publishing Scenario topics</span></span>](internet-publishing-scenario.md)
