---
title: XML 持久化格式
TOCTitle: XML Persistence Format
ms:assetid: 499f335c-ee1f-c803-e3a8-034b8decf1ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249226(v=office.15)
ms:contentKeyID: 48544643
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: e7825d55c6f0c2f900f61a325265dce048f965e5
ms.sourcegitcommit: 8fe462c32b91c87911942c188f3445e85a54137c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32308279"
---
# <a name="xml-persistence-format"></a>XML 暂留格式

**适用于**：Access 2013、Office 2013

## <a name="xml-persistence-format"></a>XML 持久化格式

ADO 对于它所持久化的 XML 流使用 UTF-8 编码。

ADO XML 格式可分成两节：架构节和数据节，架构节在前，数据节在后。下面是罗斯文数据库中 Shippers（货主）表的示例 XML 文件。该 XML 的各个部分将在该示例代码之后讨论。

```xml
<xml xmlns:s="uuid:BDC6E3F0-6DA3-11d1-A2A3-00AA00C14882"  
xmlns:dt="uuid:C2F41010-65B3-11d1-A29F-00AA00C14882"  
xmlns:rs="urn:schemas-microsoft-com:rowset"  
xmlns:z="#RowsetSchema">  
  <s:Schema id="RowsetSchema">  
    <s:ElementType name="row" content="eltOnly" rs:updatable="true">  
      <s:AttributeType name="ShipperID" rs:number="1"  
        rs:basetable="shippers" rs:basecolumn="ShipperID" 
        rs:keycolumn="true">  
        <s:datatype dt:type="int" dt:maxLength="4" rs:precision="10"  
          rs:fixedlength="true" rs:maybenull="false"/>  
      </s:AttributeType>  
      <s:AttributeType name="CompanyName" rs:number="2"  
        rs:nullable="true" rs:write="true" rs:basetable="shippers"  
        rs:basecolumn="CompanyName">  
        <s:datatype dt:type="string" dt:maxLength="40" />  
      </s:AttributeType>  
      <s:AttributeType name="Phone" rs:number="3" rs:nullable="true"  
        rs:write="true" rs:basetable="shippers"  
        rs:basecolumn="Phone">  
        <s:datatype dt:type="string" dt:maxLength="24"/>  
      </s:AttributeType>  
      <s:extends type="rs:rowbase"/>  
    </s:ElementType>  
  </s:Schema>  
 
  <rs:data>  
    <z:row ShipperID="1" CompanyName="Speedy Express"  
      Phone="(503) 555-9831"/>  
    <z:row ShipperID="2" CompanyName="United Package"  
      Phone="(503) 555-3199"/>  
    <z:row ShipperID="3" CompanyName="Federal Shipping"  
      Phone="(503) 555-9931"/>  
  </rs:data>  
</xml> 
```

该架构显示命名空间的声明、架构节和数据节。架构节中包含对 ShipperID（货主 ID）、CompanyName（公司名称）和 Phone（电话）等行的定义。

架构定义遵循 XML 数据规范，而且可以进行充分验证（但在 Internet Explorer 5 中无法进行验证）。您可以访问 [W3C XMLData 说明](https://www.w3.org/TR/1998/NOTE-XML-data-0105/)来查看此规范。目前，XML 数据是 **Recordset** 持久化所支持的唯一架构格式。

数据节中有三行包含有关货主的信息。 对于空的行集, data 节可能为空, 但必须`<rs:data>`存在标记。 如果没有数据, 则可以简单地`<rs:data>`编写标记简写。 以“rs”开头的任何标记指示它位于由 urn:schemas-microsoft-com:rowset 定义的命名空间中。 此架构的完整定义在本文档的附录部分中进行了定义。

## <a name="xml-persistence-format"></a>XML 持久化格式

ADO 对于它所持久化的 XML 流使用 UTF-8 编码。

ADO XML 格式可分成两节：架构节和数据节，架构节在前，数据节在后。下面是罗斯文数据库中 Shippers（货主）表的示例 XML 文件。该 XML 的各个部分将在该示例代码之后讨论。

```xml
<xml xmlns:s="uuid:BDC6E3F0-6DA3-11d1-A2A3-00AA00C14882"  
xmlns:dt="uuid:C2F41010-65B3-11d1-A29F-00AA00C14882"  
xmlns:rs="urn:schemas-microsoft-com:rowset"  
xmlns:z="#RowsetSchema">  
  <s:Schema id="RowsetSchema">  
    <s:ElementType name="row" content="eltOnly" rs:updatable="true">  
      <s:AttributeType name="ShipperID" rs:number="1"  
        rs:basetable="shippers" rs:basecolumn="ShipperID" 
        rs:keycolumn="true">  
        <s:datatype dt:type="int" dt:maxLength="4" rs:precision="10"  
          rs:fixedlength="true" rs:maybenull="false"/>  
      </s:AttributeType>  
      <s:AttributeType name="CompanyName" rs:number="2"  
        rs:nullable="true" rs:write="true" rs:basetable="shippers"  
        rs:basecolumn="CompanyName">  
        <s:datatype dt:type="string" dt:maxLength="40" />  
      </s:AttributeType>  
      <s:AttributeType name="Phone" rs:number="3" rs:nullable="true"  
        rs:write="true" rs:basetable="shippers"  
        rs:basecolumn="Phone">  
        <s:datatype dt:type="string" dt:maxLength="24"/>  
      </s:AttributeType>  
      <s:extends type="rs:rowbase"/>  
    </s:ElementType>  
  </s:Schema>  
 
  <rs:data>  
    <z:row ShipperID="1" CompanyName="Speedy Express"  
      Phone="(503) 555-9831"/>  
    <z:row ShipperID="2" CompanyName="United Package"  
      Phone="(503) 555-3199"/>  
    <z:row ShipperID="3" CompanyName="Federal Shipping"  
      Phone="(503) 555-9931"/>  
  </rs:data>  
</xml> 
```

该架构显示命名空间的声明、架构节和数据节。架构节中包含对 ShipperID（货主 ID）、CompanyName（公司名称）和 Phone（电话）等行的定义。

架构定义遵循 XML 数据规范，而且可以进行充分验证（但在 Internet Explorer 5 中无法进行验证）。您可以访问 [W3C XMLData 说明](https://www.w3.org/TR/1998/NOTE-XML-data-0105/)来查看此规范。目前，XML 数据是 **Recordset** 持久化所支持的唯一架构格式。

数据节中有三行包含有关货主的信息。 对于空的行集, data 节可能为空, 但必须`<rs:data>`存在标记。 如果没有数据, 则可以简单地`<rs:data>`编写标记简写。 以“rs”开头的任何标记指示它位于由 urn:schemas-microsoft-com:rowset 定义的命名空间中。 此架构的完整定义在本文档的附录部分中进行了定义。

