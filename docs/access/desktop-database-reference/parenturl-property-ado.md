---
title: ParentURL 属性 (ADO)
TOCTitle: ParentURL property (ADO)
ms:assetid: ec7ec476-6f9e-8486-fe02-74995975df5c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250200(v=office.15)
ms:contentKeyID: 48548517
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 29245960ad845587ac8f31931bdd5ce1e39a63c9
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25885883"
---
# <a name="parenturl-property-ado"></a><span data-ttu-id="12057-102">ParentURL 属性 (ADO)</span><span class="sxs-lookup"><span data-stu-id="12057-102">ParentURL property (ADO)</span></span>

<span data-ttu-id="12057-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="12057-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="12057-104">指示指向当前 [Record](record-object-ado.md) 对象的父 **Record** 的绝对 URL 字符串。</span><span class="sxs-lookup"><span data-stu-id="12057-104">Indicates an absolute URL string that points to the parent [Record](record-object-ado.md) of the current **Record** object.</span></span>

## <a name="return-value"></a><span data-ttu-id="12057-105">返回值</span><span class="sxs-lookup"><span data-stu-id="12057-105">Return value</span></span>

<span data-ttu-id="12057-106">返回一个 **String** 值，指示父 **Record** 的 URL。</span><span class="sxs-lookup"><span data-stu-id="12057-106">Returns a **String** value that indicates the URL of the parent **Record**.</span></span>

## <a name="remarks"></a><span data-ttu-id="12057-107">备注</span><span class="sxs-lookup"><span data-stu-id="12057-107">Remarks</span></span>

<span data-ttu-id="12057-p101">**ParentURL** 属性由用于打开 **Record** 对象的源决定。例如，可以通过包含 **ActiveConnection** 属性引用的目录的相对路径名称的源打开 [Record](activeconnection-property-ado.md) 。</span><span class="sxs-lookup"><span data-stu-id="12057-p101">The **ParentURL** property depends upon the source used to open the **Record** object. For example, the **Record** may be opened with a source containing a relative path name of a directory referenced by the [ActiveConnection](activeconnection-property-ado.md) property.</span></span>

<span data-ttu-id="12057-p102">假定"second"是"first"下包含的文件夹。通过以下代码打开 **Record** 对象：</span><span class="sxs-lookup"><span data-stu-id="12057-p102">Suppose "second" is a folder contained under "first". Open the **Record** object with the following:</span></span>

```vb
    record.ActiveConnection = "https://first"
    record.Open "second"
```

<span data-ttu-id="12057-112">现在， **ParentURL**属性的值是**ParentURL**属性"https://first"， **activeconnection 的值**相同。</span><span class="sxs-lookup"><span data-stu-id="12057-112">Now, the value of the **ParentURL** property is **ParentURL** property is "https://first" , the same as **ActiveConnection**.</span></span>

<span data-ttu-id="12057-113">源也可能是绝对 URL，例如，"https://first/second"。</span><span class="sxs-lookup"><span data-stu-id="12057-113">The source may also be an absolute URL such as, "https://first/second" .</span></span> <span data-ttu-id="12057-114">**ParentURL**属性值为"https://first"，上面的级别。</span><span class="sxs-lookup"><span data-stu-id="12057-114">The **ParentURL** property is then "https://first" , the level above .</span></span> <span data-ttu-id="12057-115">**ParentURL**属性值为"https://first"，"第二个"上方的级别。</span><span class="sxs-lookup"><span data-stu-id="12057-115">The **ParentURL** property is then "https://first" , the level above "second" .</span></span>

<span data-ttu-id="12057-116">以下情况下，此属性为空值：</span><span class="sxs-lookup"><span data-stu-id="12057-116">This property may be a null value if:</span></span>

- <span data-ttu-id="12057-117">当前对象没有父对象，例如，如果 **Record** 对象表示根目录。</span><span class="sxs-lookup"><span data-stu-id="12057-117">There is no parent for the current object; for example, if the **Record** object represents the root of a directory.</span></span>

- <span data-ttu-id="12057-118">**Record** 对象表示无法通过 URL 指定的实体。</span><span class="sxs-lookup"><span data-stu-id="12057-118">The **Record** object represents an entity that cannot be specified with a URL.</span></span>

<span data-ttu-id="12057-119">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="12057-119">This property is read-only.</span></span>


> [!NOTE]
> - <span data-ttu-id="12057-p104">[!注释] 此属性仅受文档源提供程序支持，如 [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md)。有关详细信息，请参阅[记录和提供程序提供的字段](records-and-provider-supplied-fields.md)。</span><span class="sxs-lookup"><span data-stu-id="12057-p104">This property is only supported by document source providers, such as the [Microsoft OLE DB Provider for Internet Publishing](microsoft-ole-db-provider-for-internet-publishing.md). For more information, see [Records and Provider-Supplied Fields](records-and-provider-supplied-fields.md).</span></span>
> - <span data-ttu-id="12057-122">[!注释] 使用 HTTP 架构的 URL 将自动调用 Microsoft OLE DB Provider for Internet Publishing。</span><span class="sxs-lookup"><span data-stu-id="12057-122">URLs using the http scheme will automatically invoke the Microsoft OLE DB Provider for Internet Publishing.</span></span> <span data-ttu-id="12057-123">有关详细信息，请参阅[绝对 URL 和相对 URL](absolute-and-relative-urls.md)。</span><span class="sxs-lookup"><span data-stu-id="12057-123">For more information, see [Absolute and Relative URLs](absolute-and-relative-urls.md).</span></span> 
> - <span data-ttu-id="12057-124">[!注释] 如果当前记录包含来自 ADO **Recordset** 的数据记录，则访问 **ParentURL** 属性将导致运行时错误，指示没有可能的 URL。</span><span class="sxs-lookup"><span data-stu-id="12057-124">If the current record contains a data record from an ADO **Recordset**, accessing the **ParentURL** property causes a run-time error, indicating that no URL is possible.</span></span>


