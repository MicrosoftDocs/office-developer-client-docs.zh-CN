---
title: 数据节 （Access 桌面数据库参考 （英文）
TOCTitle: Data section
ms:assetid: fd8d31aa-af13-a52f-5e91-20225b8df175
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250303(v=office.15)
ms:contentKeyID: 48548920
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 98215394af89df30a95fcb9c5a757368cb64d4f1
ms.sourcegitcommit: 558d09fad81f8d80b5ad0edd21934fc09c098f2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2018
ms.locfileid: "25946375"
---
# <a name="data-section"></a><span data-ttu-id="02e65-102">数据节</span><span class="sxs-lookup"><span data-stu-id="02e65-102">Data section</span></span>

<span data-ttu-id="02e65-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="02e65-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="02e65-p101">数据节定义了行集的数据以及任何挂起的更新、插入或删除。数据节可能包含零行或更多行。它可能只包含由架构定义行的一个行集内的数据。而且，如前所述，没有任何数据的列可能被省略。如果在数据节中使用属性或子元素，并且尚未在架构节中定义该构造，那么它将被静默忽略。</span><span class="sxs-lookup"><span data-stu-id="02e65-p101">The data section defines the data of the rowset along with any pending updates, insertions, or deletions. The data section may contain zero or more rows. It may only contain data from one rowset where the row is defined by the schema. Also, as noted before, columns without any data may be omitted. If an attribute or subelement is used in the data section and that construct has not been defined in the schema section, it is silently ignored.</span></span>

## <a name="string"></a><span data-ttu-id="02e65-109">字符串</span><span class="sxs-lookup"><span data-stu-id="02e65-109">String</span></span>

<span data-ttu-id="02e65-p102">必须将文本数据中的保留 XML 字符替换为合适的字符实体。例如，在公司名称“Joe's Garage”中，必须将单引号字符替换为实体。实际的行会类似如下：</span><span class="sxs-lookup"><span data-stu-id="02e65-p102">Reserved XML characters in text data must be replaced with appropriate character entities. For example, in the company name "Joe's Garage," the single quote character must be replaced by an entity. The actual row would look like:</span></span>

```xml  
<z:row CompanyName="Joe&apos;s Garage"/> 
```

<span data-ttu-id="02e65-113">以下字符是 XML 保留字符，必须将替换为字符实体: {'，"，&，\<，\>}。</span><span class="sxs-lookup"><span data-stu-id="02e65-113">The following characters are reserved in XML and must be replaced by character entities: {',",&,\<,\>}.</span></span>

## <a name="binary"></a><span data-ttu-id="02e65-114">二进制</span><span class="sxs-lookup"><span data-stu-id="02e65-114">Binary</span></span>

<span data-ttu-id="02e65-115">二进制数据采用 bin.hex 编码（即一个字节映射到两个字符，每半个字节一个字符）。</span><span class="sxs-lookup"><span data-stu-id="02e65-115">Binary data is bin.hex encoded (that is, one byte maps to two characters, one character per nibble).</span></span>

## <a name="datetime"></a><span data-ttu-id="02e65-116">DateTime</span><span class="sxs-lookup"><span data-stu-id="02e65-116">DateTime</span></span>

<span data-ttu-id="02e65-117">Variant VT\_XML 数据的数据类型不直接支持日期格式。</span><span class="sxs-lookup"><span data-stu-id="02e65-117">The variant VT\_DATE format is not directly supported by XML-Data data types.</span></span> <span data-ttu-id="02e65-118">Yyyy-月-日**T**mm: ss 正确的格式的日期与日期和时间的组件。</span><span class="sxs-lookup"><span data-stu-id="02e65-118">The correct format for dates with both a data and time component is yyyy-mm-dd**T**hh:mm:ss.</span></span>

<span data-ttu-id="02e65-119">有关指定的 XML 日期格式的详细信息，请参阅[W3C XMLData 说明](https://www.w3.org/TR/1998/NOTE-XML-data-0105/)。</span><span class="sxs-lookup"><span data-stu-id="02e65-119">For more information about date formats specified by XML, see [W3C XMLData Note](https://www.w3.org/TR/1998/NOTE-XML-data-0105/).</span></span>

<span data-ttu-id="02e65-120">XML-Data 规范定义两个等价数据类型时（例如，i4 == int），ADO 将写出友好名称，但二者都会读入。</span><span class="sxs-lookup"><span data-stu-id="02e65-120">When the XML-Data specification defines two equivalent data types (for example, i4 == int), ADO will write out the friendly name but read in both.</span></span>

## <a name="managing-pending-changes"></a><span data-ttu-id="02e65-121">管理挂起更改</span><span class="sxs-lookup"><span data-stu-id="02e65-121">Managing pending changes</span></span>

<span data-ttu-id="02e65-p104">可以在立即或批更新模式下打开 **Recordset** 。以客户端游标在批更新模式下打开时，对 **Recordset** 的所有更改都将处于挂起状态，直到调用 **UpdateBatch** 方法。如果保存 **Recordset** ，则挂起的更改也将持久化。在 XML 中，通过使用在 urn:schemas-microsoft-com:rowset 中定义的"update"元素来表示挂起更改。此外，如果行集可以更新，则必须在行的定义中将可更新的属性设置为 True。例如，若要定义一个包含挂起更改的 Shippers（货主）表，则行定义会类似如下：</span><span class="sxs-lookup"><span data-stu-id="02e65-p104">A **Recordset** can be opened in immediate or batch update mode. When opened in batch update mode with client-side cursors, all changes made to the **Recordset** are in a pending state until the **UpdateBatch** method is called. Pending changes are also persisted when the **Recordset** is saved. In XML, they are represented by the use of the "update" elements defined in urn:schemas-microsoft-com:rowset. In addition, if a rowset can be updated, the updatable property must be set to true in the definition of the row. For example, to define that the Shippers table contains pending changes, the row definition would look like the following:</span></span>

```xml 
<s:ElementType name="row" content="eltOnly" updatable="true"> 
  <s:attribute type="ShipperID"/> 
  <s:attribute type="CompanyName"/> 
  <s:attribute type="Phone"/> 
  <s:extends type="rs:rowbase"/> 
</s:ElementType> 
```

<span data-ttu-id="02e65-128">这将通知 Persistence Provider 对数据进行图面化，以便 ADO 可以构造可更新的 **Recordset** 对象。</span><span class="sxs-lookup"><span data-stu-id="02e65-128">This tells the Persistence Provider to surface data so that ADO can construct an updatable **Recordset** object.</span></span>

<span data-ttu-id="02e65-129">以下示例数据显示在持久化的文件中插入、更改和删除的表现形式：</span><span class="sxs-lookup"><span data-stu-id="02e65-129">The following sample data shows how insertions, changes, and deletions look in the persisted file:</span></span>

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

<span data-ttu-id="02e65-p105">更新将始终包含整个原始行数据，并且后跟更改行数据。更改行可能包含所有列，或只包含那些已实际更改的列。在上面的示例中，Shipper 2 的行未更改，只有 Shipper 3 的 Phone 列的值发生更改，因此该列是更改行中所包含的唯一列。Shippers 12、13 和 14 的插入行一起放在一个 rs:insert 标记下面。注意，已删除的行也可以放一起，尽管上面未显示这种情况。</span><span class="sxs-lookup"><span data-stu-id="02e65-p105">An update always contains the entire original row data followed by the changed row data. The changed row may contain all of the columns or only those columns that have actually changed. In the previous example, the row for Shipper 2 is not changed, while only the Phone column has changed values for Shipper 3 and is therefore the only column included in the changed row. The inserted rows for Shippers 12, 13, and 14 are batched together under one rs:insert tag. Note that deleted rows may also be batched together, although this is not shown above.</span></span>

