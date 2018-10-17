---
title: XML 持久化格式
TOCTitle: XML Persistence Format
ms:assetid: 499f335c-ee1f-c803-e3a8-034b8decf1ae
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249226(v=office.15)
ms:contentKeyID: 48544643
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 9db8da66ab2c7bae1f28271ae37573f06ca222d7
ms.sourcegitcommit: 19aca09c5812cfb98b68b5d4604dcaa814479df7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2018
ms.locfileid: "25467312"
---
# <a name="xml-persistence-format"></a><span data-ttu-id="fa6a1-102">XML 持久化格式</span><span class="sxs-lookup"><span data-stu-id="fa6a1-102">XML Persistence Format</span></span>

<span data-ttu-id="fa6a1-103">**适用于**： Access 2013 |Office 2013</span><span class="sxs-lookup"><span data-stu-id="fa6a1-103">**Applies to**: Access 2013 | Office 2013</span></span>

## <a name="xml-persistence-format"></a><span data-ttu-id="fa6a1-104">XML 持久化格式</span><span class="sxs-lookup"><span data-stu-id="fa6a1-104">XML Persistence Format</span></span>

<span data-ttu-id="fa6a1-105">ADO 对于它所持久化的 XML 流使用 UTF-8 编码。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-105">ADO uses UTF-8 encoding for the XML stream it persists.</span></span>

<span data-ttu-id="fa6a1-p101">ADO XML 格式可分成两节：架构节和数据节，架构节在前，数据节在后。下面是罗斯文数据库中 Shippers（货主）表的示例 XML 文件。该 XML 的各个部分将在该示例代码之后讨论。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-p101">The ADO XML format is broken into two sections, a schema section followed by the data section. The following is an example XML file for the Shippers table from the Northwind database. Various parts of the XML are discussed following the example.</span></span>

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

<span data-ttu-id="fa6a1-p102">该架构显示命名空间的声明、架构节和数据节。架构节中包含对 ShipperID（货主 ID）、CompanyName（公司名称）和 Phone（电话）等行的定义。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-p102">The schema shows the declarations of namespaces, the schema section, and the data section. The schema section contains definitions for row, ShipperID, CompanyName, and Phone.</span></span>

<span data-ttu-id="fa6a1-p103">架构定义遵循 XML 数据规范，而且可以进行充分验证（但在 Internet Explorer 5 中无法进行验证）。您可以访问 [W3C XMLData 说明](https://www.w3.org/TR/1998/NOTE-XML-data-0105/)来查看此规范。目前，XML 数据是 **Recordset** 持久化所支持的唯一架构格式。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-p103">Schema definitions conform to the XML-Data specification and are able to be fully validated (though validation will not occur in Internet Explorer 5). You can view this specification at [W3C XMLData Note](https://www.w3.org/TR/1998/NOTE-XML-data-0105/). XML-Data is the only supported schema format for **Recordset** persistence currently.</span></span>

<span data-ttu-id="fa6a1-114">数据节中有三行包含有关货主的信息。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-114">The data section has three rows containing information about shippers.</span></span> <span data-ttu-id="fa6a1-115">一个空的行集的数据部分可以为空，但`<rs:data>`标记必须存在。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-115">For an empty rowset, the data section may be empty, but the `<rs:data>` tags must be present.</span></span> <span data-ttu-id="fa6a1-116">任何数据，您可以编写标记简写，只需`<rs:data>`。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-116">With no data, you could write the tag shorthand as simply `<rs:data>`.</span></span> <span data-ttu-id="fa6a1-117">以"rs"开头的任何标记指示它位于由 urn:schemas-microsoft-com:rowset 定义的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-117">Any tag prefixed with "rs" indicates that it is in the namespace defined by urn:schemas-microsoft-com:rowset.</span></span> <span data-ttu-id="fa6a1-118">此架构的完整定义在本文档的附录部分中进行了定义。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-118">The full definition of this schema is defined in the appendix to this document.</span></span>

## <a name="xml-persistence-format"></a><span data-ttu-id="fa6a1-119">XML 持久化格式</span><span class="sxs-lookup"><span data-stu-id="fa6a1-119">XML Persistence Format</span></span>

<span data-ttu-id="fa6a1-120">ADO 对于它所持久化的 XML 流使用 UTF-8 编码。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-120">ADO uses UTF-8 encoding for the XML stream it persists.</span></span>

<span data-ttu-id="fa6a1-p105">ADO XML 格式可分成两节：架构节和数据节，架构节在前，数据节在后。下面是罗斯文数据库中 Shippers（货主）表的示例 XML 文件。该 XML 的各个部分将在该示例代码之后讨论。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-p105">The ADO XML format is broken into two sections, a schema section followed by the data section. The following is an example XML file for the Shippers table from the Northwind database. Various parts of the XML are discussed following the example.</span></span>

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

<span data-ttu-id="fa6a1-p106">该架构显示命名空间的声明、架构节和数据节。架构节中包含对 ShipperID（货主 ID）、CompanyName（公司名称）和 Phone（电话）等行的定义。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-p106">The schema shows the declarations of namespaces, the schema section, and the data section. The schema section contains definitions for row, ShipperID, CompanyName, and Phone.</span></span>

<span data-ttu-id="fa6a1-p107">架构定义遵循 XML 数据规范，而且可以进行充分验证（但在 Internet Explorer 5 中无法进行验证）。您可以访问 [W3C XMLData 说明](https://www.w3.org/TR/1998/NOTE-XML-data-0105/)来查看此规范。目前，XML 数据是 **Recordset** 持久化所支持的唯一架构格式。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-p107">Schema definitions conform to the XML-Data specification and are able to be fully validated (though validation will not occur in Internet Explorer 5). You can view this specification at [W3C XMLData Note](https://www.w3.org/TR/1998/NOTE-XML-data-0105/). XML-Data is the only supported schema format for **Recordset** persistence currently.</span></span>

<span data-ttu-id="fa6a1-129">数据节中有三行包含有关货主的信息。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-129">The data section has three rows containing information about shippers.</span></span> <span data-ttu-id="fa6a1-130">一个空的行集的数据部分可以为空，但`<rs:data>`标记必须存在。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-130">For an empty rowset, the data section may be empty, but the `<rs:data>` tags must be present.</span></span> <span data-ttu-id="fa6a1-131">任何数据，您可以编写标记简写，只需`<rs:data>`。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-131">With no data, you could write the tag shorthand as simply `<rs:data>`.</span></span> <span data-ttu-id="fa6a1-132">以"rs"开头的任何标记指示它位于由 urn:schemas-microsoft-com:rowset 定义的命名空间中。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-132">Any tag prefixed with "rs" indicates that it is in the namespace defined by urn:schemas-microsoft-com:rowset.</span></span> <span data-ttu-id="fa6a1-133">此架构的完整定义在本文档的附录部分中进行了定义。</span><span class="sxs-lookup"><span data-stu-id="fa6a1-133">The full definition of this schema is defined in the appendix to this document.</span></span>
