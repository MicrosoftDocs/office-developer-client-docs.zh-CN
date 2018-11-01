---
title: XML 中的分层记录集
TOCTitle: Hierarchical Recordsets in XML
ms:assetid: 606dee87-8762-6cc2-a151-94d34031b35f
ms:mtpsurl: https://msdn.microsoft.com/library/JJ249351(v=office.15)
ms:contentKeyID: 48545181
ms.date: 09/18/2015
mtps_version: v=office.15
ms.openlocfilehash: 5276dd011ec8b7c6190ab35f5417009510875e15
ms.sourcegitcommit: c557bbcccf37a6011f89aae1ddd399dfe549d087
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2018
ms.locfileid: "25877168"
---
# <a name="hierarchical-recordsets-in-xml"></a><span data-ttu-id="c40b8-102">XML 中的分层记录集</span><span class="sxs-lookup"><span data-stu-id="c40b8-102">Hierarchical Recordsets in XML</span></span>


<span data-ttu-id="c40b8-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="c40b8-103">**Applies to**: Access 2013, Office 2013</span></span>

## <a name="hierarchical-recordsets-in-xml"></a><span data-ttu-id="c40b8-104">XML 中的分层记录集</span><span class="sxs-lookup"><span data-stu-id="c40b8-104">Hierarchical Recordsets in XML</span></span>

<span data-ttu-id="c40b8-p101">ADO 允许将分层 **Recordset** 对象持久化到 XML 中。使用分层 **Recordset** 对象，父 **Recordset** 中的字段值将是另一个 **Recordset** 。这样的字段在 XML 流中将表示为子元素而不是属性。以下示例演示了这种情况：</span><span class="sxs-lookup"><span data-stu-id="c40b8-p101">ADO allows persistence of hierarchical **Recordset** objects into XML. With hierarchical **Recordset** objects, the value of a field in the parent **Recordset** is another **Recordset**. Such fields are represented as child elements in the XML stream rather than an attribute. The following example demonstrates this case:</span></span>

```vb 
 
Rs.Open "SHAPE {select stor_id, stor_name, state from stores} APPEND ({select stor_id, ord_num, ord_date, qty from sales} AS rsSales RELATE stor_id TO stor_id)", "Provider=MSDataShape;DSN=pubs;UID=MyUserId;PWD=MyPassword;" 
```

<span data-ttu-id="c40b8-109">下面是持久化的 **Recordset** 的 XML 格式：</span><span class="sxs-lookup"><span data-stu-id="c40b8-109">The following is the XML format of the persisted **Recordset**:</span></span>

```xml 
 
<xml xmlns:s="uuid:BDC6E3F0-6DA3-11d1-A2A3-00AA00C14882"     xmlns:dt="uuid:C2F41010-65B3-11d1-A29F-00AA00C14882"     xmlns:rs="urn:schemas-microsoft-com:rowset"  
    xmlns:z="#RowsetSchema">  
  <s:Schema id="RowsetSchema">  
    <s:ElementType name="row" content="eltOnly" rs:updatable="true">  
      <s:AttributeType name="stor_id" rs:number="1"  
        rs:writeunknown="true">  
        <s:datatype dt:type="string" dt:maxLength="4"  
          rs:fixedlength="true" rs:maybenull="false"/>  
      </s:AttributeType>  
      <s:AttributeType name="stor_name" rs:number="2" rs:nullable="true"  
        rs:writeunknown="true">  
          <s:datatype dt:type="string" dt:maxLength="40"/>  
      </s:AttributeType>  
      <s:AttributeType name="state" rs:number="3" rs:nullable="true"  
        rs:writeunknown="true">  
        <s:datatype dt:type="string" dt:maxLength="2"  
          rs:fixedlength="true"/>  
      </s:AttributeType>  
      <s:ElementType name="rsSales" content="eltOnly"  
        rs:updatable="true" rs:relation="010000000100000000000000">  
        <s:AttributeType name="stor_id" rs:number="1"  
          rs:writeunknown="true">  
          <s:datatype dt:type="string" dt:maxLength="4"  
            rs:fixedlength="true" rs:maybenull="false"/>  
        </s:AttributeType>  
        <s:AttributeType name="ord_num" rs:number="2"  
          rs:writeunknown="true">  
          <s:datatype dt:type="string" dt:maxLength="20"  
            rs:maybenull="false"/>  
        </s:AttributeType>  
        <s:AttributeType name="ord_date" rs:number="3"  
          rs:writeunknown="true">  
            <s:datatype dt:type="dateTime" dt:maxLength="16"  
              rs:scale="3" rs:precision="23" rs:fixedlength="true"  
              rs:maybenull="false"/>  
        </s:AttributeType>  
        <s:AttributeType name="qty" rs:number="4" rs:writeunknown="true">  
          <s:datatype dt:type="i2" dt:maxLength="2" rs:precision="5"  
            rs:fixedlength="true" rs:maybenull="false"/>  
        </s:AttributeType>  
        <s:extends type="rs:rowbase"/>  
      </s:ElementType>  
      <s:extends type="rs:rowbase"/>  
    </s:ElementType>  
  </s:Schema>  
  <rs:data>  
    <z:row stor_id="6380" stor_name="Eric the Read Books" state="WA">  
      <rsSales stor_id="6380" ord_num="6871"  
        ord_date="1994-09-14T00:00:00" qty="5"/>  
      <rsSales stor_id="6380" ord_num="722a"  
        ord_date="1994-09-13T00:00:00" qty="3"/>  
    </z:row>  
    <z:row stor_id="7066" stor_name="Barnum's" state="CA">  
      <rsSales stor_id="7066" ord_num="A2976"  
        ord_date="1993-05-24T00:00:00" qty="50"/>  
      <rsSales stor_id="7066" ord_num="QA7442.3"  
        ord_date="1994-09-13T00:00:00" qty="75"/>  
    </z:row>  
    <z:row stor_id="7067" stor_name="News & Brews" state="CA">  
      <rsSales stor_id="7067" ord_num="D4482"  
        ord_date="1994-09-14T00:00:00" qty="10"/>  
      <rsSales stor_id="7067" ord_num="P2121"  
        ord_date="1992-06-15T00:00:00" qty="40"/>  
      <rsSales stor_id="7067" ord_num="P2121"  
        ord_date="1992-06-15T00:00:00" qty="20"/>  
      <rsSales stor_id="7067" ord_num="P2121"  
        ord_date="1992-06-15T00:00:00" qty="20"/>  
    </z:row>  
... 
  </rs:data>  
</xml>  
```

<span data-ttu-id="c40b8-p102">以此方式持久化父 **Recordset** 时，其列的确切顺序是不明显的。父对象中的任何字段都可能包含子 **Recordset** 。Persistence Provider 首先将所有标量列作为属性持久化出来，然后将所有子 **Recordset** 的"列"作为父行的子元素持久化出来。通过查看 **Recordset** 的架构定义，可以获得父 **Recordset** 中字段的序号位置。每个字段都有 OLE DB 属性 **rs:number** ，该属性是在包含该字段序号的 **Recordset** 架构命名空间中定义的。</span><span class="sxs-lookup"><span data-stu-id="c40b8-p102">The exact order of the columns in the parent **Recordset** is not obvious when it is persisted in this manner. Any field in the parent may contain a child **Recordset**. The Persistence Provider persists out all scalar columns first as attributes and then persists out all child **Recordset** "columns" as child elements of the parent row. The ordinal position of the field in the parent **Recordset** can be obtained by looking at the schema definition of the **Recordset**. Every field has an OLE DB property, **rs:number**, defined in the **Recordset** schema namespace that contains the ordinal number for that field.</span></span>

<span data-ttu-id="c40b8-p103">子 **Recordset** 中所有字段的名称都与包含该子对象的父 **Recordset** 中的字段的名称串联在一起。这是为了确保万一父和子 **Recordset** 都包含从两个不同表获得的同名字段时，不会有名称冲突。</span><span class="sxs-lookup"><span data-stu-id="c40b8-p103">The names of all fields in the child **Recordset** are concatenated with the name of the field in the parent **Recordset** that contains this child. This is to ensure that there are no name collisions in cases where parent and child **Recordsets** both contain a field that is obtained from two different tables but is named singularly.</span></span>

<span data-ttu-id="c40b8-117">将分层 **Recordset** 保存到 XML 中时，应当知道 ADO 中的以下限制：</span><span class="sxs-lookup"><span data-stu-id="c40b8-117">When saving hierarchical **Recordsets** into XML, you should be aware of the following restrictions in ADO:</span></span>

  - <span data-ttu-id="c40b8-118">具有挂起更新的分层 **Recordset** 无法持久化到 XML 中。</span><span class="sxs-lookup"><span data-stu-id="c40b8-118">A hierarchical **Recordset** with pending updates cannot be persisted into XML.</span></span>

  - <span data-ttu-id="c40b8-119">以参数化 Shape 命令创建的分层 **Recordset** 无法持久化（以 XML 或 ADTG 格式）。</span><span class="sxs-lookup"><span data-stu-id="c40b8-119">A hierarchical **Recordset** created with a parameterized shape command cannot be persisted (in either XML or ADTG format).</span></span>

  - <span data-ttu-id="c40b8-p104">ADO 目前将父和子 **Recordset** 之间的关系作为二进制大型对象 (BLOB) 进行保存。在行集架构命名空间中，尚未定义用于描述此关系的 XML 标记。</span><span class="sxs-lookup"><span data-stu-id="c40b8-p104">ADO currently saves the relationship between the parent and the child **Recordsets** as a binary large object (BLOB). XML tags to describe this relationship have not yet been defined in the rowset schema namespace.</span></span>

  - <span data-ttu-id="c40b8-p105">保存分层 **Recordset** 时，所有子 **Recordset** 都将与它一起保存。如果当前 **Recordset** 是另一个 **Recordset** 的子对象，则不保存它的父对象。构成当前 **Recordset** 的子树的所有子 **Recordset** 都会保存。</span><span class="sxs-lookup"><span data-stu-id="c40b8-p105">When a hierarchical **Recordset** is saved, all child **Recordsets** are saved along with it. If the current **Recordset** is a child of another **Recordset**, its parent is not saved. All child **Recordsets** that form the subtree of the current **Recordset** are saved.</span></span>

<span data-ttu-id="c40b8-125">从其 XML 持久化的格式重新打开分层 **Recordset** 时，必须知道以下限制：</span><span class="sxs-lookup"><span data-stu-id="c40b8-125">When a hierarchical **Recordset** is reopened from its XML-persisted format, you must be aware of the following limitations:</span></span>

  - <span data-ttu-id="c40b8-p106">如果子记录包含的记录没有相应的父记录，则这些行不以分层 **Recordset** 的 XML 表示形式写出。因此，从其持久化的位置重新打开 **Recordset** 时，将丢失这些行。</span><span class="sxs-lookup"><span data-stu-id="c40b8-p106">If the child record contains records for which there are no corresponding parent records, these rows are not written out in the XML representation of the hierarchical **Recordset**. Thus, these rows will be lost when the **Recordset** is reopened from its persisted location.</span></span>

  - <span data-ttu-id="c40b8-p107">如果子记录引用了多个父记录，则重新打开该 **Recordset** ，子 **Recordset** 可能包含重复记录。但是，只有当用户直接处理基础子行集时，这些重复才是可见的。如果用章节来导航子 **Recordset** （这是在 ADO 中导航的唯一方式），则重复是不可见的。</span><span class="sxs-lookup"><span data-stu-id="c40b8-p107">If a child record has references to more than one parent record, then on reopening the **Recordset**, the child **Recordset** may contain duplicate records. However, these duplicates will only be visible if the user works directly with the underlying child rowset. If a chapter is used to navigate the child **Recordset** (that is the only way to navigate through ADO), the duplicates are not visible.</span></span>

