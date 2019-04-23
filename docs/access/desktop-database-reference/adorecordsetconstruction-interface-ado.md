---
title: ADORecordsetConstruction 接口 (ADO)
TOCTitle: ADORecordsetConstruction interface (ADO)
ms:assetid: 2b53aa6e-3b6f-a996-3967-534215fd586c
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249060(v=office.15)
ms:contentKeyID: 48543926
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 98342d5456c545e6da8539c11f616c08fd52a932
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32281631"
---
# <a name="adorecordsetconstruction-interface-ado"></a>ADORecordsetConstruction 接口 (ADO)


**适用于**：Access 2013、Office 2013

**ADORecordsetConstruction** 接口用于通过 C/C++ 应用程序中的 OLE DB **Rowset** 对象构造 ADO **Recordset** 对象。

此接口支持以下属性：

## <a name="properties"></a>属性

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="chapter-property-ado.md">第二章</a></p></td>
<td><p>读/写。<br />
获取/设置此 ADO <strong>Recordset</strong> 对象上的 OLE DB <strong>Chapter</strong> 对象。</p></td>
</tr>
<tr class="even">
<td><p><a href="rowposition-property-ado.md">RowPosition</a></p></td>
<td><p>读/写。<br />

获取/设置此 ADO <strong>Recordset</strong> 对象上的 OLE DB <strong>RowPosition</strong> 对象。</p></td>
</tr>
<tr class="odd">
<td><p><a href="rowset-property-ado.md">Rowset</a></p></td>
<td><p>读/写。<br />

获取/设置此 ADO <strong>Recordset</strong> 对象上的 OLE DB <strong>Rowset</strong> 对象。</p></td>
</tr>
</tbody>
</table>


## <a name="methods"></a>方法

无。

## <a name="events"></a>事件

无。

## <a name="remarks"></a>注解

给定一个 OLE DB **Rowset**对象 (pRowset), 即 ado **recordset**对象 () 的构造, 将 ado **recordset**对象 (adoRs) 的构造量构造为以下三个基本操作:

1. 创建 ADO **Recordset** 对象：
    
   ```vb
    Recordset20Ptr adoRs;
    adoRs.CreateInstance(__uuidof(Recordset));
   ```
2. 查询 **Recordset** 对象上的 **IADORecordsetConstruction** 接口：

   ```vb    
    adoRecordsetConstructionPtr adoRsConstruct=NULL;
    adoRs->QueryInterface(__uuidof(ADORecordsetConstruction),
         (void**)&adoRsConstruct);
   ```

3. 调用 IADORecordsetConstruction::p 工作项\_行集属性方法来设置 ADO Recordset 对象上的 OLE DB 行集对象:

   ```vb     
    IUnknown *pUnk=NULL;
    pRowset->QueryInterface(IID_IUnknown, (void**)&pUnk);
    adoRsConstruct->put_Rowset(pUnk);
   ```
生成的对象现在表示从 OLE DB **Rowset**对象构造的 ADO **Recordset**对象。

还可以通过 OLE DB **Chapter** 或 **RowPosition** 对象构造 ADO **Recordset**。

## <a name="requirements"></a>Requirements

- **版本：** ADO 2.0 及更高版本

- **库：** msado15.dll

- **UUID：** 00000283-0000-0010-8000-00AA006D2EA4

