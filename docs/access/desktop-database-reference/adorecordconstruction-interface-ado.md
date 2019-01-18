---
title: ADORecordConstruction 接口 (ADO)
TOCTitle: ADORecordConstruction interface (ADO)
ms:assetid: 3f0afbdb-f1c4-e44e-7c0f-a0c4cee554a7
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249175(v=office.15)
ms:contentKeyID: 48544387
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1a53eb107bab0d31606dc161b9f9c910894c5bc6
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28712006"
---
# <a name="adorecordconstruction-interface-ado"></a><span data-ttu-id="d5b78-102">ADORecordConstruction 接口 (ADO)</span><span class="sxs-lookup"><span data-stu-id="d5b78-102">ADORecordConstruction interface (ADO)</span></span>


<span data-ttu-id="d5b78-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d5b78-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d5b78-104">**ADORecordConstruction** 接口用于根据 C/C++ 应用程序中的 OLE DB **Row** 对象构造 ADO **Record** 对象。</span><span class="sxs-lookup"><span data-stu-id="d5b78-104">The **ADORecordConstruction** interface is used to construct an ADO **Record** object from an OLE DB **Row** object in a C/C++ application.</span></span>

<span data-ttu-id="d5b78-105">此接口支持以下属性：</span><span class="sxs-lookup"><span data-stu-id="d5b78-105">This interface supports the following properties:</span></span>

## <a name="properties"></a><span data-ttu-id="d5b78-106">属性</span><span class="sxs-lookup"><span data-stu-id="d5b78-106">Properties</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d5b78-107"><a href="parentrow-property-ado.md">ParentRow</a></span><span class="sxs-lookup"><span data-stu-id="d5b78-107"><a href="parentrow-property-ado.md">ParentRow</a></span></span></p></td>
<td><p><span data-ttu-id="d5b78-108">为只写属性。</span><span class="sxs-lookup"><span data-stu-id="d5b78-108">Write-only.</span></span><br />
<span data-ttu-id="d5b78-109">在此 ADO <strong>Record</strong>对象上设置 OLE DB <strong>Row</strong>对象的容器。</span><span class="sxs-lookup"><span data-stu-id="d5b78-109">Sets the container of an OLE DB <strong>Row</strong> object on this ADO <strong>Record</strong> object.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d5b78-110"><a href="row-property-ado.md">行</a></span><span class="sxs-lookup"><span data-stu-id="d5b78-110"><a href="row-property-ado.md">Row</a></span></span></p></td>
<td><p><span data-ttu-id="d5b78-111">读/写。</span><span class="sxs-lookup"><span data-stu-id="d5b78-111">Read/Write.</span></span><br />
<span data-ttu-id="d5b78-112">获取/设置从在此 ADO <strong>Record</strong>对象的 OLE DB <strong>Row</strong>对象。</span><span class="sxs-lookup"><span data-stu-id="d5b78-112">Gets/sets an OLE DB <strong>Row</strong> object from/on this ADO <strong>Record</strong> object.</span></span></p></td>
</tr>
</tbody>
</table>


## <a name="methods"></a><span data-ttu-id="d5b78-113">方法</span><span class="sxs-lookup"><span data-stu-id="d5b78-113">Methods</span></span>

<span data-ttu-id="d5b78-114">无。</span><span class="sxs-lookup"><span data-stu-id="d5b78-114">None.</span></span>

## <a name="events"></a><span data-ttu-id="d5b78-115">事件</span><span class="sxs-lookup"><span data-stu-id="d5b78-115">Events</span></span>

<span data-ttu-id="d5b78-116">无。</span><span class="sxs-lookup"><span data-stu-id="d5b78-116">None.</span></span>

## <a name="remarks"></a><span data-ttu-id="d5b78-117">备注</span><span class="sxs-lookup"><span data-stu-id="d5b78-117">Remarks</span></span>

<span data-ttu-id="d5b78-118">给定 OLE DB **Row**对象 (pRow)、 构造的 ADO **Record**对象 （）、 构造 ADO **Record**对象 (adoR) 量与以下三个基本操作：</span><span class="sxs-lookup"><span data-stu-id="d5b78-118">Given an OLE DB **Row** object (pRow), the construction of an ADO **Record** object (), the construction of an ADO **Record** object (adoR), amounts to the following three basic operations:</span></span>

1.  <span data-ttu-id="d5b78-119">创建 ADO **Record** 对象：</span><span class="sxs-lookup"><span data-stu-id="d5b78-119">Create an ADO **Record** object:</span></span>
    
    ```vb
        _RecordPtr adoR;
        adoRs.CreateInstance(__uuidof(_Record));
    ```

2.  <span data-ttu-id="d5b78-120">查询 **Record** 对象的 **IADORecordConstruction** 接口：</span><span class="sxs-lookup"><span data-stu-id="d5b78-120">Query the **IADORecordConstruction** interface on the **Record** object:</span></span>
    
    ```vb
        adoRecordConstructionPtr adoRConstruct=NULL;
        adoR->QueryInterface(__uuidof(ADORecordConstruction),
                            (void**)&adoRConstruct);
    ```

3.  <span data-ttu-id="d5b78-121">调用**IADORecordConstruction::put\_行**属性方法，以便设置 ADO **Record**对象的 OLE DB **Row**对象：</span><span class="sxs-lookup"><span data-stu-id="d5b78-121">Call the **IADORecordConstruction::put\_Row** property method to set the OLE DB **Row** object on the ADO **Record** object:</span></span>
    
    ```vb
        IUnknown *pUnk=NULL;
        pRow->QueryInterface(IID_IUnknown, (void**)&pUnk);
        adoRConstruct->put_Row(pUnk);
    ```
    
<span data-ttu-id="d5b78-122">产生的 **adoR** 对象现在表示根据 OLE DB **Row** 对象构造的 ADO **Record** 对象。</span><span class="sxs-lookup"><span data-stu-id="d5b78-122">The resultant **adoR** object now represents the ADO **Record** object constructed from the OLE DB **Row** object.</span></span>

<span data-ttu-id="d5b78-123">也可以根据 OLE DB **Row** 对象的容器构造 ADO **Record** 对象。</span><span class="sxs-lookup"><span data-stu-id="d5b78-123">An ADO **Record** object can also be constructed from the container of an OLE DB **Row** object.</span></span>

## <a name="requirements"></a><span data-ttu-id="d5b78-124">要求</span><span class="sxs-lookup"><span data-stu-id="d5b78-124">Requirements</span></span>

<span data-ttu-id="d5b78-125">**版本：** ADO 2.0 及更高版本</span><span class="sxs-lookup"><span data-stu-id="d5b78-125">**Version:** ADO 2.0 and later</span></span>

<span data-ttu-id="d5b78-126">**库：** msado15.dll</span><span class="sxs-lookup"><span data-stu-id="d5b78-126">**Library:** msado15.dll</span></span>

<span data-ttu-id="d5b78-127">**UUID：** 00000567-0000-0010-8000-00AA006D2EA4</span><span class="sxs-lookup"><span data-stu-id="d5b78-127">**UUID:** 00000567-0000-0010-8000-00AA006D2EA4</span></span>

