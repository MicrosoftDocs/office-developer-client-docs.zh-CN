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
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281624"
---
# <a name="adorecordconstruction-interface-ado"></a>ADORecordConstruction 接口 (ADO)


**适用于**：Access 2013、Office 2013

**ADORecordConstruction** 接口用于根据 C/C++ 应用程序中的 OLE DB **Row** 对象构造 ADO **Record** 对象。

此接口支持以下属性：

## <a name="properties"></a>属性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="parentrow-property-ado.md">ParentRow</a></p></td>
<td><p>只写。<br />

设置此 ADO <strong>Record</strong> 对象中 OLE DB <strong>Row</strong> 对象的容器。</p></td>
</tr>
<tr class="even">
<td><p><a href="row-property-ado.md">行</a></p></td>
<td><p>读/写。<br />

获取/设置此 ADO <strong>Record</strong> 对象中的 OLE DB <strong>Row</strong> 对象。</p></td>
</tr>
</tbody>
</table>


## <a name="methods"></a>方法

无。

## <a name="events"></a>事件

无。

## <a name="remarks"></a>注解

给定一个 OLE DB **Row**对象 (pRow)、ado **record**对象 () 的构造、ado **record**对象 (adoR) 的构造以及以下三个基本操作:

1.  创建 ADO **Record** 对象：
    
    ```vb
        _RecordPtr adoR;
        adoRs.CreateInstance(__uuidof(_Record));
    ```

2.  查询 **Record** 对象的 **IADORecordConstruction** 接口：
    
    ```vb
        adoRecordConstructionPtr adoRConstruct=NULL;
        adoR->QueryInterface(__uuidof(ADORecordConstruction),
                            (void**)&adoRConstruct);
    ```

3.  调用**IADORecordConstruction::p 工作的\_行**属性方法, 以设置 ADO **Record**对象上的 OLE DB **row**对象:
    
    ```vb
        IUnknown *pUnk=NULL;
        pRow->QueryInterface(IID_IUnknown, (void**)&pUnk);
        adoRConstruct->put_Row(pUnk);
    ```
    
产生的 **adoR** 对象现在表示根据 OLE DB **Row** 对象构造的 ADO **Record** 对象。

也可以根据 OLE DB **Row** 对象的容器构造 ADO **Record** 对象。

## <a name="requirements"></a>Requirements

**版本：** ADO 2.0 及更高版本

**库：** msado15.dll

**UUID：** 00000567-0000-0010-8000-00AA006D2EA4

