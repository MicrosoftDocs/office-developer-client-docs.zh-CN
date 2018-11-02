---
title: ADORecordsetConstruction 接口 (ADO)
TOCTitle: ADORecordsetConstruction interface (ADO)
ms:assetid: 2b53aa6e-3b6f-a996-3967-534215fd586c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249060(v=office.15)
ms:contentKeyID: 48543926
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 8ab9723d3acc698aa36210e26e370c0edfa67728
ms.sourcegitcommit: d7248f803002b31cf7fc561b03530199a9b0a8fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2018
ms.locfileid: "25924230"
---
# <a name="adorecordsetconstruction-interface-ado"></a><span data-ttu-id="a177b-102">ADORecordsetConstruction 接口 (ADO)</span><span class="sxs-lookup"><span data-stu-id="a177b-102">ADORecordsetConstruction interface (ADO)</span></span>


<span data-ttu-id="a177b-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="a177b-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="a177b-104">**ADORecordsetConstruction** 接口用于通过 C/C++ 应用程序中的 OLE DB **Rowset** 对象构造 ADO **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="a177b-104">The **ADORecordsetConstruction** interface is used to construct an ADO **Recordset** object from an OLE DB **Rowset** object in a C/C++ application.</span></span>

<span data-ttu-id="a177b-105">此接口支持以下属性：</span><span class="sxs-lookup"><span data-stu-id="a177b-105">This interface supports the following properties:</span></span>

## <a name="properties"></a><span data-ttu-id="a177b-106">属性</span><span class="sxs-lookup"><span data-stu-id="a177b-106">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a177b-107"><a href="chapter-property-ado.md">章</a></span><span class="sxs-lookup"><span data-stu-id="a177b-107"><a href="chapter-property-ado.md">Chapter</a></span></span></p></td>
<td><p><span data-ttu-id="a177b-108">读/写。</span><span class="sxs-lookup"><span data-stu-id="a177b-108">Read/Write.</span></span><br />
<span data-ttu-id="a177b-109">获取/设置从/上此 ADO <strong>Recordset</strong>对象的 OLE DB <strong>Chapter</strong>对象。</span><span class="sxs-lookup"><span data-stu-id="a177b-109">Gets/sets an OLE DB <strong>Chapter</strong> object from/on this ADO <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a177b-110"><a href="rowposition-property-ado.md">RowPosition</a></span><span class="sxs-lookup"><span data-stu-id="a177b-110"><a href="rowposition-property-ado.md">RowPosition</a></span></span></p></td>
<td><p><span data-ttu-id="a177b-111">读/写。</span><span class="sxs-lookup"><span data-stu-id="a177b-111">Read/Write.</span></span><br />
<span data-ttu-id="a177b-112">获取/设置从/上此 ADO <strong>Recordset</strong>对象的 OLE DB <strong>RowPosition</strong>对象。</span><span class="sxs-lookup"><span data-stu-id="a177b-112">Gets/sets an OLE DB <strong>RowPosition</strong> object from/on this ADO <strong>Recordset</strong> object.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a177b-113"><a href="rowset-property-ado.md">行集</a></span><span class="sxs-lookup"><span data-stu-id="a177b-113"><a href="rowset-property-ado.md">Rowset</a></span></span></p></td>
<td><p><span data-ttu-id="a177b-114">读/写。</span><span class="sxs-lookup"><span data-stu-id="a177b-114">Read/Write.</span></span><br />
<span data-ttu-id="a177b-115">获取/设置从/上此 ADO <strong>Recordset</strong>对象的 OLE DB <strong>Rowset</strong>对象。</span><span class="sxs-lookup"><span data-stu-id="a177b-115">Gets/sets an OLE DB <strong>Rowset</strong> object from/on this ADO <strong>Recordset</strong> object.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="methods"></a><span data-ttu-id="a177b-116">方法</span><span class="sxs-lookup"><span data-stu-id="a177b-116">Methods</span></span>

<span data-ttu-id="a177b-117">无。</span><span class="sxs-lookup"><span data-stu-id="a177b-117">None.</span></span>

## <a name="events"></a><span data-ttu-id="a177b-118">事件</span><span class="sxs-lookup"><span data-stu-id="a177b-118">Events</span></span>

<span data-ttu-id="a177b-119">无。</span><span class="sxs-lookup"><span data-stu-id="a177b-119">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="a177b-120">说明</span><span class="sxs-lookup"><span data-stu-id="a177b-120">Remarks</span></span>

<span data-ttu-id="a177b-121">(PRowset) OLE DB **Rowset**对象构造的 ADO **Recordset**对象 （）、 构造的 ADO **Recordset**对象 (adoRs) 金额赋予以下三个基本操作：</span><span class="sxs-lookup"><span data-stu-id="a177b-121">Given an OLE DB **Rowset** object (pRowset ), the construction of an ADO **Recordset** object (), the construction of an ADO **Recordset** object (adoRs ) amounts to the following three basic operations:</span></span>

1. <span data-ttu-id="a177b-122">创建 ADO **Recordset** 对象：</span><span class="sxs-lookup"><span data-stu-id="a177b-122">Create an ADO **Recordset** object:</span></span>
    
   ```vb
    Recordset20Ptr adoRs;
    adoRs.CreateInstance(__uuidof(Recordset));
   ```
2. <span data-ttu-id="a177b-123">查询 **Recordset** 对象上的 **IADORecordsetConstruction** 接口：</span><span class="sxs-lookup"><span data-stu-id="a177b-123">Query the **IADORecordsetConstruction** interface on the **Recordset** object:</span></span>

   ```vb    
    adoRecordsetConstructionPtr adoRsConstruct=NULL;
    adoRs->QueryInterface(__uuidof(ADORecordsetConstruction),
         (void**)&adoRsConstruct);
   ```

3. <span data-ttu-id="a177b-124">调用 IADORecordsetConstruction::put\_Rowset 属性方法，以便设置 ADO Recordset 对象的 OLE DB Rowset 对象：</span><span class="sxs-lookup"><span data-stu-id="a177b-124">Call the IADORecordsetConstruction::put\_Rowset property method to set the OLE DB Rowset object on the ADO Recordset object:</span></span>

   ```vb     
    IUnknown *pUnk=NULL;
    pRowset->QueryInterface(IID_IUnknown, (void**)&pUnk);
    adoRsConstruct->put_Rowset(pUnk);
   ```
<span data-ttu-id="a177b-125">结果的对象现在表示从 OLE DB **Rowset**对象构造的 ADO **Recordset**对象。</span><span class="sxs-lookup"><span data-stu-id="a177b-125">The resultant object now represents the ADO **Recordset** object constructed from the OLE DB **Rowset** object.</span></span>

<span data-ttu-id="a177b-126">还可以通过 OLE DB **Chapter** 或 **RowPosition** 对象构造 ADO **Recordset** 。</span><span class="sxs-lookup"><span data-stu-id="a177b-126">You can also construct an ADO **Recordset** object from an OLE DB **Chapter** or **RowPosition** object.</span></span>

## <a name="requirements"></a><span data-ttu-id="a177b-127">要求</span><span class="sxs-lookup"><span data-stu-id="a177b-127">Requirements</span></span>

- <span data-ttu-id="a177b-128">**版本：** ADO 2.0 及更高版本</span><span class="sxs-lookup"><span data-stu-id="a177b-128">**Version:** ADO 2.0 and later</span></span>

- <span data-ttu-id="a177b-129">**库：** msado15.dll</span><span class="sxs-lookup"><span data-stu-id="a177b-129">**Library:** msado15.dll</span></span>

- <span data-ttu-id="a177b-130">**UUID：** 00000283-0000-0010-8000-00AA006D2EA4</span><span class="sxs-lookup"><span data-stu-id="a177b-130">**UUID:** 00000283-0000-0010-8000-00AA006D2EA4</span></span>

