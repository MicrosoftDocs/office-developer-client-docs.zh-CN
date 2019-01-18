---
title: 数据节 （Access 桌面数据库参考 （英文）
TOCTitle: Data section
ms:assetid: fd8d31aa-af13-a52f-5e91-20225b8df175
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250303(v=office.15)
ms:contentKeyID: 48548920
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 1b8e3baf4d147edcc739e59933da4697c08cdef0
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28700771"
---
# <a name="data-section"></a>数据部分

**适用于**： Access 2013、 Office 2013

数据节定义了行集的数据以及任何挂起的更新、插入或删除。数据节可能包含零行或更多行。它可能只包含由架构定义行的一个行集内的数据。而且，如前所述，没有任何数据的列可能被省略。如果在数据节中使用属性或子元素，并且尚未在架构节中定义该构造，那么它将被静默忽略。

## <a name="string"></a>字符串

必须将文本数据中的保留 XML 字符替换为合适的字符实体。例如，在公司名称“Joe's Garage”中，必须将单引号字符替换为实体。实际的行会类似如下：

```xml  
<z:row CompanyName="Joe&apos;s Garage"/> 
```

以下字符是 XML 保留字符，必须将替换为字符实体: {'，"，&，\<，\>}。

## <a name="binary"></a>二进制

二进制数据采用 bin.hex 编码（即一个字节映射到两个字符，每半个字节一个字符）。

## <a name="datetime"></a>日期/时间

Variant VT\_XML 数据的数据类型不直接支持日期格式。 Yyyy-月-日**T**mm: ss 正确的格式的日期与日期和时间的组件。

有关指定的 XML 日期格式的详细信息，请参阅[W3C XMLData 说明](https://www.w3.org/TR/1998/NOTE-XML-data-0105/)。

XML-Data 规范定义两个等价数据类型时（例如，i4 == int），ADO 将写出友好名称，但二者都会读入。

## <a name="managing-pending-changes"></a>管理挂起更改

可以在立即或批更新模式下打开 **Recordset** 。以客户端游标在批更新模式下打开时，对 **Recordset** 的所有更改都将处于挂起状态，直到调用 **UpdateBatch** 方法。如果保存 **Recordset** ，则挂起的更改也将持久化。在 XML 中，通过使用在 urn:schemas-microsoft-com:rowset 中定义的"update"元素来表示挂起更改。此外，如果行集可以更新，则必须在行的定义中将可更新的属性设置为 True。例如，若要定义一个包含挂起更改的 Shippers（货主）表，则行定义会类似如下：

```xml 
<s:ElementType name="row" content="eltOnly" updatable="true"> 
  <s:attribute type="ShipperID"/> 
  <s:attribute type="CompanyName"/> 
  <s:attribute type="Phone"/> 
  <s:extends type="rs:rowbase"/> 
</s:ElementType> 
```

这将通知 Persistence Provider 对数据进行图面化，以便 ADO 可以构造可更新的 **Recordset** 对象。

以下示例数据显示在持久化的文件中插入、更改和删除的表现形式：

```xml 
<rs:data> 
  <z:row ShipperID="2" CompanyName="United Package"  
    Phone="(503) 555-3199"/> 
<rs:update> 
  <rs:original> 
    <z:row ShipperID="3" CompanyName="Federal Shipping"  
      Phone="(503) 555-9931"/> 
  </rs:original> 
  <z:row Phone="(503) 552-7134"/> 
</rs:update> 
<rs:insert> 
  <z:row ShipperID="12" CompanyName="Lightning Shipping"  
    Phone="(505) 111-2222"/> 
  <z:row ShipperID="13" CompanyName="Thunder Overnight"  
    Phone="(505) 111-2222"/> 
  <z:row ShipperID="14" CompanyName="Blue Angel Air Delivery"  
    Phone="(505) 111-2222"/> 
</rs:insert> 
<rs:delete> 
  <z:row ShipperID="1" CompanyName="Speedy Express" Phone="(503) 555-9831"/> 
</rs:delete> 
</rs:data> 
```

更新将始终包含整个原始行数据，并且后跟更改行数据。更改行可能包含所有列，或只包含那些已实际更改的列。在上面的示例中，Shipper 2 的行未更改，只有 Shipper 3 的 Phone 列的值发生更改，因此该列是更改行中所包含的唯一列。Shippers 12、13 和 14 的插入行一起放在一个 rs:insert 标记下面。注意，已删除的行也可以放一起，尽管上面未显示这种情况。

