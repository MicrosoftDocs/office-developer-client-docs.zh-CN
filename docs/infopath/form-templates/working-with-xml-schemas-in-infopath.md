---
title: 在 InfoPath 中使用 XML 架构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: c1d70e9f-b9fc-7bdb-107e-d0cd8191607b
description: 使用 Microsoft InfoPath 创建的表单模板可以通过 XML 架构 (XSD)，对从 InfoPath 表单输入、编辑和输出的 XML 执行结构和数据验证。在 InfoPath 表单设计器中创建的每个表单模板都至少包含一个 XSD 架构文件 (.xsd)，该架构文件用于在运行时进行验证。
ms.openlocfilehash: 6b19399e4f31f6270fa6f360a8428c725050ce16
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22568271"
---
# <a name="working-with-xml-schemas-in-infopath"></a><span data-ttu-id="b3c28-104">在 InfoPath 中使用 XML 架构</span><span class="sxs-lookup"><span data-stu-id="b3c28-104">Working with XML Schemas in InfoPath</span></span>

<span data-ttu-id="b3c28-p102">使用 Microsoft InfoPath 创建的表单模板可以通过 XML 架构 (XSD)，对从 InfoPath 表单输入、编辑和输出的 XML 执行结构和数据验证。在 InfoPath 表单设计器中创建的每个表单模板都至少包含一个 XSD 架构文件 (.xsd)，该架构文件用于在运行时进行验证。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p102">A form template that you create with Microsoft InfoPath uses an XML Schema (XSD) to perform structural and data validation on the XML that is input, edited, and output from an InfoPath form. Every form template created in the InfoPath form designer contains at least one XSD schema file (.xsd) that is used for validation at run time.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b3c28-p103">本主题中包含的信息适用于为在 InfoPath 编辑器中使用而设计的表单模板。浏览器兼容的表单模板具有更为严格的 XSD 架构要求。有关详细信息，请参阅 MSDN 上提供的有关浏览器兼容的表单模板中的 XML 架构的文档。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p103">The information contained in this topic applies to form templates designed for use in the InfoPath editor. Browser-compatible form templates have stricter XSD Schema requirements. For more information, see the documentation about XML Schemas in browser-compatible form templates available on MSDN.</span></span> 
  
## <a name="using-externally-authored-xml-schemas"></a><span data-ttu-id="b3c28-110">使用外部编写的 XML 架构</span><span class="sxs-lookup"><span data-stu-id="b3c28-110">Using Externally-authored XML Schemas</span></span>

<span data-ttu-id="b3c28-111">若要加载在 InfoPath 以外编写的 XSD 架构文件，请执行下列步骤。</span><span class="sxs-lookup"><span data-stu-id="b3c28-111">To load an XSD schema file that was authored outside of InfoPath, follow these steps.</span></span>
  
### <a name="to-create-a-form-template-based-on-an-external-schema"></a><span data-ttu-id="b3c28-112">基于外部架构创建表单模板</span><span class="sxs-lookup"><span data-stu-id="b3c28-112">To create a form template based on an external schema</span></span>

1. <span data-ttu-id="b3c28-113">在 Backstage 中，单击“新建”****，在“高级表单模板”**** 下单击“XML 或架构”****，然后单击“设计此表单”****。</span><span class="sxs-lookup"><span data-stu-id="b3c28-113">In the Backstage, click **New**, click **XML or Schema** under **Advanced Form Templates**, and then click **Design This Form**.</span></span>
    
2. <span data-ttu-id="b3c28-114">在“数据源向导”**** 中，指定要使用的 XSD 架构文件，然后单击“下一步”**** 并完成向导的其余页面。</span><span class="sxs-lookup"><span data-stu-id="b3c28-114">In the **Data Source Wizard**, specify the XSD schema file you want to use, and then click **Next** and complete the remaining pages of the wizard.</span></span> 
    
## <a name="unsupported-xsd-constructs"></a><span data-ttu-id="b3c28-115">不受支持的 XSD 构造</span><span class="sxs-lookup"><span data-stu-id="b3c28-115">Unsupported XSD Constructs</span></span>

<span data-ttu-id="b3c28-p104">以下部分描述了 InfoPath 在运行时无法处理的 XSD 构造。在 InfoPath 表单设计器中创建表单模板时，应避免使用这些构造。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p104">The following sections describe XSD constructs that InfoPath cannot handle at run time. Avoid these constructs when creating a form template in the InfoPath form designer.</span></span>
  
## <a name="entity-and-entities-types"></a><span data-ttu-id="b3c28-118">ENTITY 和 ENTITIES 类型</span><span class="sxs-lookup"><span data-stu-id="b3c28-118">ENTITY and ENTITIES Types</span></span>

<span data-ttu-id="b3c28-p105">**ENTITY** 和 **ENTITIES** 类型需要文档类型定义 (DTD) 来进行验证，而 InfoPath 不支持 DTD。InfoPath 不允许根据这种架构设计表单模板，并且会显示一条错误消息，建议您将 **ENTITY** 类型改为 **NCName** 类型（ **ENTITY** 派生自该类型）。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p105">The **ENTITY** and **ENTITIES** types require a document type definition (DTD) for validation, which InfoPath does not support. InfoPath does not allow you to design a form template against such a schema and displays an error message that recommends changing the **ENTITY** type to the **NCName** type from which **ENTITY** derives.</span></span> 
  
> [!NOTE]
>  <span data-ttu-id="b3c28-121">如果您在设计模式之外手动编写了一个 InfoPath 表单模板，并且该表单模板使用了包括 **ENTITY** 和 **ENTITIES** 类型的 XSD，当 Template.xml 文件包含这些类型所必需的 DTD 时，该 InfoPath 表单模板在运行时或许可以工作。</span><span class="sxs-lookup"><span data-stu-id="b3c28-121">If you manually author an InfoPath form template outside of design mode, and it uses an XSD that includes **ENTITY** and **ENTITIES** types, the form template may work at run time if the Template.xml file contains the required DTD for these types.</span></span> 
  
## <a name="required-xsdany-element"></a><span data-ttu-id="b3c28-122">必需的 xsd:any 元素</span><span class="sxs-lookup"><span data-stu-id="b3c28-122">Required xsd:any Element</span></span>

<span data-ttu-id="b3c28-p106">如果存在 **xsd:any** 通配符元素，即存在 **minOccurs** 属性值大于零（“required any”）的 **xsd:any** 元素，则会明确阻止 InfoPath 创建此架构片段的有效实例。InfoPath 必须能够创建此架构片段的有效实例，才能生成使用此架构片段的表单。在运行“数据源向导”**** 的过程中，包含必需的 **xsd:any** 元素的架构要求您选择要使用的架构元素，以代替必需的 **xsd:any** 元素。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p106">An occurrence of an **xsd:any** wildcard element, that is, an occurrence of an **xsd:any** element with a **minOccurs** attribute value greater than zero ("required any"), prevents InfoPath from deterministically creating a valid instance for this schema fragment. InfoPath must be able to create a valid instance when generating a form that uses this schema fragment. As part of running the **Data Source Wizard**, schemas with required **xsd:any** elements require you to choose which schema element you want to use in place of the required **xsd:any** element.</span></span> 
  
## <a name="elements-with-an-abstract-complex-type"></a><span data-ttu-id="b3c28-126">具有抽象复杂类型的元素</span><span class="sxs-lookup"><span data-stu-id="b3c28-126">Elements with an Abstract Complex Type</span></span>

<span data-ttu-id="b3c28-p107">InfoPath 设计模式支持根据使用抽象复杂类型的架构设计表单模板。例如，如果一个名为  `shippingAddress` 的元素有一个名为  `address` 的抽象复杂类型，该类型具有两个派生类型：  `USAddress` 和  `CanadianAddress`，则 InfoPath 会将  `shippingAddress` 的任意实例视为在以下二者间进行选择：类型为  `shippingAddress` 的  `USAddress` 或类型为  `shippingAddress` 的  `CanadianAddress`。在本例中，如果提供的架构不包含从地址派生的类型，则 InfoPath 会请求另一个满足此要求的架构。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p107">InfoPath design mode supports designing a form template against schemas that use abstract complex types. For example, if an element named  `shippingAddress` has an abstract complex type named  `address` that has two derivations,  `USAddress` and  `CanadianAddress`, InfoPath treats any instance of  `shippingAddress` as a choice between  `shippingAddress` with type  `USAddress` and  `shippingAddress` with type  `CanadianAddress` . In this example, if the provided schemas contain no types that derive from address, then InfoPath requests an additional schema that fulfills this requirement.</span></span> 
  
## <a name="xsd-constructs-with-reduced-functionality"></a><span data-ttu-id="b3c28-130">具有缩简功能的 XSD 构造</span><span class="sxs-lookup"><span data-stu-id="b3c28-130">XSD Constructs with Reduced Functionality</span></span>

<span data-ttu-id="b3c28-131">以下部分描述的 XSD 构造用于在 InfoPath 表单设计器中创建表单模板时，功能有所缩减。</span><span class="sxs-lookup"><span data-stu-id="b3c28-131">The following sections describe XSD constructs that have reduced functionality when used to create a form template in the InfoPath form designer.</span></span>
  
## <a name="substitution-groups"></a><span data-ttu-id="b3c28-132">替换组</span><span class="sxs-lookup"><span data-stu-id="b3c28-132">Substitution Groups</span></span>

<span data-ttu-id="b3c28-p108">替换组的所有成员都显示在“域”**** 任务窗格中。InfoPath 将可能的替换项表示为所有替换组中的一个选项（不是抽象元素的定义元素也包括在内）。如果某个抽象元素没有替换组，则 InfoPath 会提示您提供一个架构，其中至少包含一个作为替换组的元素。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p108">All members of the substitution group appear in the **Fields** task pane. InfoPath represents the substitution possibilities as a choice of all the substitution groups (including the defining element, if it is not abstract). If there are no substitution groups for an abstract element, InfoPath prompts you to provide a schema that contains at least one element that is a substitution group.</span></span> 
  
## <a name="unbounded-choice-elements"></a><span data-ttu-id="b3c28-136">无限次选项元素</span><span class="sxs-lookup"><span data-stu-id="b3c28-136">Unbounded Choice Elements</span></span>

<span data-ttu-id="b3c28-137">以下架构片段显示了一个无限次选项元素：</span><span class="sxs-lookup"><span data-stu-id="b3c28-137">The following schema fragment shows an unbounded choice element:</span></span>
  
```XML
<xsd:choice maxOccurs="unbounded"> 
    <xsd:element name="my_element_1"/> 
    <xsd:element name="my_element_2"/> 
</xsd:choice> 

```

<span data-ttu-id="b3c28-p109">InfoPath 将重复选项元素作为重复选项显示在“域”**** 任务窗格中。这里有一个“重复选项组”**** 控件，可以用来表示由 XSD 中的重复选项元素所定义的异类列表。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p109">InfoPath displays repeating choice elements as repeating choices in the **Fields** task pane. There is a **Repeating Choice Group** control that you can use to represent the heterogeneous list defined by the repeating choice element in the XSD.</span></span> 
  
## <a name="repeating-sequence"></a><span data-ttu-id="b3c28-140">重复序列</span><span class="sxs-lookup"><span data-stu-id="b3c28-140">Repeating Sequence</span></span>

<span data-ttu-id="b3c28-141">以下架构片段显示了一个重复序列：</span><span class="sxs-lookup"><span data-stu-id="b3c28-141">The following schema fragment shows a repeating sequence:</span></span>
  
```XML
<xsd:sequence maxOccurs="unbounded"> 
    <xsd:element name="my_element_1"/> 
    <xsd:element name="my_element_2" minOccurs="0"/> 
</xsd:sequence> 

```

<span data-ttu-id="b3c28-142">只要重复序列中包含必需的元素，InfoPath 就会不加修改地加载 XSD，并且允许您将重复节控件绑定到重复序列。</span><span class="sxs-lookup"><span data-stu-id="b3c28-142">As long as the repeating sequence contains a required element, InfoPath loads the XSD without modifying it and allows you to bind repeating section controls to the repeating sequence.</span></span>
  
## <a name="choice-of-model-groups"></a><span data-ttu-id="b3c28-143">模型组选项</span><span class="sxs-lookup"><span data-stu-id="b3c28-143">Choice of Model Groups</span></span>

<span data-ttu-id="b3c28-144">以下架构片段显示了包含若干模型组的选项元素：</span><span class="sxs-lookup"><span data-stu-id="b3c28-144">The following schema fragment shows the choice element containing several model groups:</span></span>
  
```XML
<xsd:choice> 
    <xsd:element name="my_element_1"/> 
    <xsd:sequence> 
        <xsd:element name="my_element_2"/> 
        <xsd:element name="my_element_3"/> 
    </xsd:sequence> 
</xsd:choice> 

```

<span data-ttu-id="b3c28-p110">InfoPath 设计模式支持此类 XSD 构造，并且不要求表单设计人员做任何修改。尽管 InfoPath 不会修改架构的含义，但是它会将上述选项构造简化为“域”**** 任务窗格中折叠起来的单个对等选项。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p110">InfoPath design mode supports such XSD constructs without requiring any modification by the form designer. While InfoPath does not modify the meaning of the schema, it simplifies the choice construct above into an equivalent collapsed single choice in the **Fields** task pane.</span></span> 
  
## <a name="optional-sibling-with-same-qualified-name"></a><span data-ttu-id="b3c28-147">具有相同限定名称的可选同级元素</span><span class="sxs-lookup"><span data-stu-id="b3c28-147">Optional Sibling with Same Qualified Name</span></span>

<span data-ttu-id="b3c28-148">以下架构片段显示了具有相同限定名称 (`QName`) 的可选同级元素：</span><span class="sxs-lookup"><span data-stu-id="b3c28-148">The following schema fragment shows an optional sibling with same qualified name (`QName`):</span></span>
  
```xml
<xsd:sequence> 
    <xsd:element name="my_element_1" minOccurs="0"/> 
    <xsd:element name="my_element_2"/> 
            <xsd:element name="my_element_1"/> 
</xsd:sequence> 

```

<span data-ttu-id="b3c28-p111">这些节点的 **XPath** 表达式可能非常复杂，原因是每个潜在的 XML 实例都必须包括在 InfoPath 表单设计器内。InfoPath 在为某些架构部分创建正确的 **XPath** 绑定时可能会遇到困难，因此它不会公开这些部分，而是显示有关这些被忽略的架构部分的警告。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p111">**XPath** expressions for these nodes can be complex because every potential XML instance must be accounted for in the InfoPath form designer. InfoPath does not expose parts of the schema for which it may have difficulty creating correct **XPath** bindings. Warnings appear regarding the portions of the schema that are ignored.</span></span> 
  
## <a name="xsd-constructs-with-special-meaning-in-infopath"></a><span data-ttu-id="b3c28-152">在 InfoPath 中具有特殊含义的 XSD 构造</span><span class="sxs-lookup"><span data-stu-id="b3c28-152">XSD Constructs with Special Meaning in InfoPath</span></span>

<span data-ttu-id="b3c28-p112">以下部分描述的 XSD 构造用于在设计模式中创建表单模板时，有着特殊含义。这些部分描述了如何在架构中使用这些构造来实现特定的行为。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p112">The following sections describe XSD constructs that have special meaning when used in creating a form template in design mode. These sections describe how you can use the constructs in your schema to enable certain behaviors.</span></span>
  
## <a name="adding-new-element-fields-and-groups-with-the-fields-task-pane"></a><span data-ttu-id="b3c28-155">使用"域"任务窗格添加新的元素域和组</span><span class="sxs-lookup"><span data-stu-id="b3c28-155">Adding New Element Fields and Groups with the Fields Task Pane</span></span>

<span data-ttu-id="b3c28-p113">您可以对架构进行设计，以便可以使用“域”**** 任务窗格，在设计时向元素中添加新的元素域和组。为此，需要使用通过 **##any** 通配符指定命名空间属性的、可选的无限次 **xsd:any** 元素在架构中声明一个元素。然后，在设计模式下，可以使用“域”**** 任务窗格将新的元素域和组添加到该元素中。例如，可以将新内容添加到以下元素中：</span><span class="sxs-lookup"><span data-stu-id="b3c28-p113">You can construct your schema so that you can use the **Fields** task pane to add new element fields and groups to an element at design time. To do so, you declare an element in your schema with an optional, unbounded **xsd:any** element that specifies the namespace attribute with the **##any** wildcard. Then, in design mode, you can use the **Fields** task pane to add new element fields and groups to that element. For example, you could add new content to the following element:</span></span> 
  
```XML
<xsd:element name="open"> 
    <xsd:complexType> 
         <xsd:sequence> 
             <xsd:any minOccurs="0" maxOccurs="unbounded" namespace="##any"processContents="lax"/> 
         </xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

## <a name="adding-new-attribute-fields-with-the-fields-task-pane"></a><span data-ttu-id="b3c28-160">使用"域"任务窗格添加新的属性域</span><span class="sxs-lookup"><span data-stu-id="b3c28-160">Adding New Attribute Fields with the Fields Task Pane</span></span>

<span data-ttu-id="b3c28-p114">与元素的情况类似，您也可以使用将命名空间属性指定为 **##any** 通配符的 **anyAttribute** 元素来声明一个属性。在设计时，可以使用“域”**** 任务窗格将新的内容添加到该架构属性中。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p114">Similarly to the element case, you can declare an attribute with an **anyAttribute** element that has the namespace attribute specified as the **##any** wildcard. At design time, you can use the **Fields** task pane to add new content to that schema attribute.</span></span> 
  
```XML
<xsd:element name="open"> 
    <xsd:complexType> 
        <xsd:anyAttribute namespace="##any" processContents="lax"/> 
    </xsd:complexType> 
</xsd:element> 

```

## <a name="storing-xml-signatures-in-the-data-source"></a><span data-ttu-id="b3c28-163">将 XML 签名存储在数据源中</span><span class="sxs-lookup"><span data-stu-id="b3c28-163">Storing XML Signatures in the Data Source</span></span>

<span data-ttu-id="b3c28-p115">若要使用户能够在运行时对表单进行数字签名，数据源的架构必须声明一个名为 signature 的元素，用于存储用户在对表单进行签名时所创建的 XML 签名（数字签名）信息。可以使用 **xsd:any** 元素来实现此声明，该元素将命名空间属性指定为带通配符的 XML 签名命名空间，例如"http://www.w3c.org/2000/09/xmldsig#"：</span><span class="sxs-lookup"><span data-stu-id="b3c28-p115">To enable users to digitally sign a form at run time, the schema of the data source must declare an element named signature for storing the XML Signatures (digital signature) information that is created when a user signs the form. You make this declaration by using the **xsd:any** element with the namespace attribute specified as the XML Signatures namespace with a wildcard character, as follows: "http://www.w3c.org/2000/09/xmldsig#"</span></span> 
  
```XML
<xsd:element name="signature"> 
    <xsd:complexType> 
        <xsd:sequence> 
            <xsd:any namespace="http://www.w3c.org/2000/09/xmldsig#"  
             processContents="lax" minOccurs="0" maxOccurs="unbounded"/> 
        <xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

## <a name="binding-a-field-to-a-rich-text-box-control"></a><span data-ttu-id="b3c28-166">将域绑定到格式文本框控件</span><span class="sxs-lookup"><span data-stu-id="b3c28-166">Binding a Field to a Rich Text Box Control</span></span>

 <span data-ttu-id="b3c28-p116">InfoPath 中的“格式文本框”**** 控件会生成通用 XHTML；因此，您的架构必须指定任意数量的文本和 XHTML 节点在表单实例的 XML 中都有效。可以使用以下 XSD 构造进行指定：</span><span class="sxs-lookup"><span data-stu-id="b3c28-p116">**Rich Text Box** controls in InfoPath generate generic XHTML; consequently, your schema must specify that any number of text and XHTML nodes is valid in the XML of the form instance. You can achieve this specification with the following XSD construct:</span></span> 
  
```XML
<xsd:element name="xhtml"> 
    <xsd:complexType mixed="true"> 
        <xsd:sequence> 
            <xsd:any minOccurs="0" maxOccurs="unbounded" namespace="http://www.w3.org/1999/xhtml" processContents="lax"/> 
        </xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

> [!NOTE]
> <span data-ttu-id="b3c28-p117">InfoPath 从不修改架构文件 (.xsd) 的内容，但它可能会为了设计目的，从逻辑上推断架构文件的子集。无论在设计时还是在运行时，表单模板内的架构文件都始终保持不变。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p117">InfoPath never modifies the content of the schema file (.xsd), but it may logically infer a subset of it for design purposes. The schema file is always untouched within the form template at both design time and run time.</span></span> 
  
## <a name="debugging-common-xsd-errors"></a><span data-ttu-id="b3c28-171">调试常见 XSD 错误</span><span class="sxs-lookup"><span data-stu-id="b3c28-171">Debugging Common XSD Errors</span></span>

<span data-ttu-id="b3c28-p118">如果您加载在外部编写的 XSD 文件，以便在 InfoPath 表单设计器中创建表单模板，则可能收到以下两种错误消息之一：MSXML 错误消息或 InfoPath 错误消息。MSXML 错误消息出现在 InfoPath 错误消息对话框的“详细信息”**** 部分，并且始终以引用正在引发此错误的架构文件的名称或路径开头。某些有效的 XSD 架构不受 InfoPath 支持；“不受支持的 XSD 构造”部分讨论了这些 XSD 构造。以下部分描述了一些会导致在 InfoPath 中无法成功加载架构的常见错误。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p118">If you load externally authored XSD files to create form templates in the InfoPath form designer, you may receive either of two types of error messages: MSXML error messages or InfoPath error messages. MSXML error messages appear in the **Details** section of an InfoPath error message dialog box, and they always begin with a reference to the name or path of the schema file that is raising the error. Some valid XSD schema constructs are not supported by InfoPath; these are discussed in the Unsupported XSD Constructs section. The following sections describe some common errors that can cause schemas to fail to load successfully in InfoPath.</span></span> 
  
## <a name="the-xsd-namespace-declaration"></a><span data-ttu-id="b3c28-176">XSD 命名空间声明</span><span class="sxs-lookup"><span data-stu-id="b3c28-176">The XSD Namespace Declaration</span></span>

<span data-ttu-id="b3c28-p119">与所有 W3C 标准类似，XML 架构 (XSD) 在成为一项建议标准之前，也经历了漫长的评审过程，产生了大量的工作草案，因此，有很多 XSD 文件是基于这些逐渐完善的标准编写的。在此过程中，Microsoft 创建了一种称为"简化 XML 数据"(XDR) 的专有架构语言，该语言随 MSXML 3.0 提供。从发布 MSXML 4.0 开始，Microsoft XML Core Services 支持完整的 XSD 建议。很多用来创建架构的程序没有等到 XSD 变成一项完整建议，这些程序的旧版本可能创建了 InfoPath 所依赖的 MSXML 5.0 基础架构不支持的过时 XSD 文件。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p119">Similar to all W3C standards, XML Schemas (XSD) went through a lengthy review process on its way to becoming a recommendation. There were many working drafts, and consequently, many XSD files were written based on these evolving standards. During this process, Microsoft created a proprietary schema language called XML-Data Reduced (XDR) that was included with MSXML 3.0. Starting with the release of MSXML 4.0, Microsoft XML Core Services supports the full recommendation of XSD. Many programs for creating schemas did not wait for XSD to become a full recommendation. Older versions of these programs may produce outdated XSD files that the MSXML 5.0 infrastructure, on which InfoPath depends, does not support.</span></span>
  
<span data-ttu-id="b3c28-183">为了确保 XSD 文件支持完整的 XSD 建议，XSD 文件应在 \<schema\> 标记中包含以下 XML 命名空间声明：</span><span class="sxs-lookup"><span data-stu-id="b3c28-183">To ensure that an XSD file supports the full XSD recommendation, it should contain the following XML namespace declaration in the \<schema\> tag:</span></span>
  
```XML
xmlns:xsd="http://www.w3.org/2001/XMLSchema"
```

<span data-ttu-id="b3c28-p120">与所有 XML 命名空间声明类似，XML 前缀（这里为"xsd"）可以是任何有效的前缀字符串。在实际操作中可能会看到的一些常用前缀有"xsd"、"xs"和""（无前缀）。如果缺少该命名空间声明，则 MSXML 通常会报告有关"根未正确定义"错误。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p120">Similar to all XML namespace declarations, the XML prefix (in this case 'xsd') can be any valid prefix string. Some common prefixes you may see in practice are 'xsd', 'xs', and '' (no prefix). MSXML usually reports an error about the root not being properly defined if this namespace declaration is missing.</span></span>
  
## <a name="importing-and-including-schemas"></a><span data-ttu-id="b3c28-187">导入和包含架构</span><span class="sxs-lookup"><span data-stu-id="b3c28-187">Importing and Including Schemas</span></span>

<span data-ttu-id="b3c28-p121">XSD 架构可以扩展，并且可以导入和包含其他架构。一般而言，如果 **targetNamespace** 属性中指定的架构与当前架构不同，则应导入架构。如果 **targetNamespace** 属性中指定的架构与当前架构相同，则应包含架构。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p121">XSD schemas are extensible and can import and include other schemas. Generally, you should import a schema if the schema specified in the **targetNamespace** attribute differs from the current schema. You should include it if the schema specified in the **targetNamespace** attribute is the same as the current schema.</span></span> 
  
<span data-ttu-id="b3c28-191">导入和包含架构的语义如下：</span><span class="sxs-lookup"><span data-stu-id="b3c28-191">The semantics for importing and including schemas are as follows:</span></span>
  
```XML
<xsd:import namespace = "[anyURI]" schemaLocation = "[anyURI]"/> 
<xsd:include schemaLocation = "[anyURI]"/> 

```

<span data-ttu-id="b3c28-p122">如果 **schemaLocation** 属性缺失（就像在某些转换器中那样），则 MSXML 会因找不到文件而引发错误。如果收到此错误，还应进行检查以确保表单模板的用户能够访问在 schemaLocation 属性中指定的资源或位置。很明显，如果 **schemaLocation** 属性引用的服务器或目录已关闭或不存在，或者用户无访问权限，就会发生错误。另外，一定要检查所有导入和包含的架构，以确保其有效。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p122">If the **schemaLocation** attribute is missing (as happens with some converters), then MSXML raises an error because it cannot find the file. If you get this error, also check to make sure that the resource or location specified in the schemaLocation attribute is accessible by users of the form template. Obviously, errors occur if the **schemaLocation** attribute references a server or directory that is down or nonexistent or if users do not have access permissions. Also, be sure to examine all imported and included schemas to make sure they are valid.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="b3c28-p123">仅当 InfoPath 首次导入架构，即您第一次基于现有架构开始设计表单时，因 **schemaLocation** 属性问题引发的错误才成为问题。此后，InfoPath 将使用存储在表单模板中的架构文件的缓存版本。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p123">Errors caused by problems with the **schemaLocation** attribute are an issue only when InfoPath first imports the schemas; that is, when you first start designing a form based on an existing schema. After that, InfoPath works with cached versions of the schema files that are stored in the form template.</span></span> 
  
<span data-ttu-id="b3c28-p124">在导入架构时，如果该架构没有指定 **targetNamespace** 属性，则允许使用空的命名空间属性。通常，导入时使用的命名空间必须与在要导入的架构中指定的 **targetNamespace** 相符。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p124">An empty namespace attribute is allowed when importing a schema, if that schema does not specify a **targetNamespace** attribute. In general, the namespace on the import must match the **targetNamespace** specified in the schema that you import.</span></span> 
  
## <a name="nondeterministic-schemas"></a><span data-ttu-id="b3c28-200">非确定性架构</span><span class="sxs-lookup"><span data-stu-id="b3c28-200">Nondeterministic Schemas</span></span>

<span data-ttu-id="b3c28-p125">InfoPath 所依赖的 MSXML 5.0 基础结构会可靠地检测和引发错误，以提醒您注意非确定性架构，但生成的错误消息中不提供行号，因此您无从知道究竟是架构的哪一部分引发了错误。本节讨论的主题就是，为什么对于 XSD 架构文件而言确定性很重要，以及非确定性意味着什么。另外还显示一些应避免的常见错误。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p125">The MSXML 5.0 infrastructure that InfoPath depends upon can reliably detect and raise errors to alert you to nondeterministic schemas, but the resultant error message does not provide a line number to tell you which part of the schema is raising the error. This section discusses why it is important for XSD schema files to be deterministic and what it means to be nondeterministic. It also shows some common errors to avoid.</span></span>
  
<span data-ttu-id="b3c28-p126">XSD 架构存在的目的是为了验证 XML 数据结构和类型语义。为完成此任务，验证系统（这里为 MSXML 5.0）必须将 XML 节点映射到 XSD 声明。如果不进行这种映射，验证系统将无法完成其任务。如果能保证实现映射，则架构就是确定性的。如果有一个 XML 实例使这种映射无法实现，则架构就是非确定性的。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p126">XSD schemas exist for the purpose of validating XML data structure and type semantics. To accomplish this task, the validating system (in this case, MSXML 5.0) must map XML nodes to XSD declarations. Without this mapping, the validating system cannot accomplish its task. If a mapping can be guaranteed, then the schema is deterministic. If there is a single XML instance that makes this mapping impossible, then the schema is nondeterministic.</span></span>
  
<span data-ttu-id="b3c28-209">以下示例架构为非确定性的：</span><span class="sxs-lookup"><span data-stu-id="b3c28-209">The following example schema is nondeterministic:</span></span>
  
```XML
<xsd:element name="file_Information"> 
    <xsd:complexType> 
        <xsd:sequence> 
            <xsd:element name="file_name"/> 
            <xsd:choice> 
                <xsd:element name="file_path"/> 
                <xsd:sequence> 
                    <xsd:element name="file_path" minOccurs="0"/> 
                    <xsd:element name="URI"/> 
                </xsd:sequence> 
            </xsd:choice> 
        </xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

<span data-ttu-id="b3c28-210">为了阐释此 XSD 片段为什么是非确定性的，在此假设您拥有以下 XML 片段，您要使用此架构对其进行验证：</span><span class="sxs-lookup"><span data-stu-id="b3c28-210">To illustrate why this XSD segment is nondeterministic, assume you have the following XML fragment that you want to validate with this schema:</span></span>
  
```XML
<file_Information> 
    <file_name>my_Schema.xsd</file_name> 
    <file_path>c:\xsd</file_path> 
</file_Information> 

```

<span data-ttu-id="b3c28-p127">在此 XML 片段中，没有指明  *\<file_path\>*  元素是来自选项声明第一部分的必需节点，还是来自选项声明第二部分的可选节点。这种区分非常重要，原因如下：</span><span class="sxs-lookup"><span data-stu-id="b3c28-p127">In this XML fragment, it is not clear whether the  *\<file_path\>*  element is the required node from the first part of the choice declaration or the optional one from the second part of the choice declaration. This distinction is important for the following reasons:</span></span> 
  
1. <span data-ttu-id="b3c28-213">如果根据选项声明的第一部分验证 XML 片段，则 XML 对于架构有效。</span><span class="sxs-lookup"><span data-stu-id="b3c28-213">If the XML fragment is validated against the first part of the choice declaration, then the XML is valid against the schema.</span></span>
    
2. <span data-ttu-id="b3c28-214">如果根据选项声明的第二部分验证 XML 片段，则因为缺少必需的 \<URI\> 节点，架构无效。</span><span class="sxs-lookup"><span data-stu-id="b3c28-214">If the XML fragment is validated against the second part of the choice declaration, then the schema is not valid, because the required \<URI\> node is missing.</span></span> 
    
<span data-ttu-id="b3c28-p128">因为存在有效路径，所以有些 XSD 验证系统在针对此架构进行验证时会发生错误。MSXML 更为严格，它会引发一个错误，指明架构为非确定性架构。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p128">Some XSD validation systems err toward validating against this schema because there is a valid path. MSXML is stricter and raises an error stating that the schema is nondeterministic.</span></span>
  
<span data-ttu-id="b3c28-p129">下面再给出几个非确定性架构的示例。第一个示例涉及可选元素。这些情况通常源于 XDR 到 XSD 转换器，因为这两种架构语言的默认基数不同。要考虑的第一种情况是使用 **xsd:choice** 和 **xsd:sequence** 元素声明的可选元素。对于在 **xsd:sequence** 元素中声明的可选元素，只要同名元素的出现次数不超过一次，并且中间只有可选元素，通常就能够正确验证这些可选元素。例如：</span><span class="sxs-lookup"><span data-stu-id="b3c28-p129">What follows are a few more examples of nondeterministic schemas. The first deals with optional elements. These cases often arise from XDR to XSD converters because of differences in the default cardinalities in the two schema languages. The first case to consider is optional elements declared with **xsd:choice** and **xsd:sequence** elements. Optional elements declared in an **xsd:sequence** element usually validate properly, as long as you do not have elements with the same name more than once, with only optional elements in between. For example:</span></span> 
  
```XML
<xsd:element name="container"> 
    <xsd:complexType> 
        <xsd:sequence> 
            <xsd:element ref="aNode" /> 
            <xsd:element ref="anotherNode" minOccurs="0"/> 
            <xsd:element ref="aNode" /> 
        </xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

<span data-ttu-id="b3c28-223">为了理解此架构片段为什么是非确定性的，在此假设您拥有以下无效 XML 片段：</span><span class="sxs-lookup"><span data-stu-id="b3c28-223">To understand why this schema segment is nondeterministic, assume you have the following invalid XML fragment:</span></span>
  
```XML
<container> 
    <aNode/> 
    <aNode/> 
    <anotherNode/> 
</container> 

```

<span data-ttu-id="b3c28-224">观察此片段，您会看出它为什么是无效的： `<aNode>` 元素前面有两个  `<anotherNode>` 元素，但实际上只允许有一个。</span><span class="sxs-lookup"><span data-stu-id="b3c28-224">Looking at this fragment, you can see why it is invalid: there are two  `<aNode>` elements before the  `<anotherNode>` element, when only one is allowed.</span></span> 
  
<span data-ttu-id="b3c28-225">现在假设您具有以下要验证的 XML 实例：</span><span class="sxs-lookup"><span data-stu-id="b3c28-225">Now assume that you have the following XML instance to validate:</span></span>
  
```XML
<container> 
    <aNode/> 
    <aNode/> 
</container> 

```

<span data-ttu-id="b3c28-p130">难点在于判断该实例是否有效。您是拥有两个  `<aNode>` 元素，但只允许其中之一？还是两个  `<aNode>` 元素都允许？无从知道答案，因此该架构是非确定性的。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p130">The challenge is to determine whether this instance is valid. Do you have two  `<aNode>` elements where only one is allowed, or do you have an  `<aNode>` element where it is allowed and another where it is allowed? The schema is nondeterministic because there is no way to know.</span></span> 
  
<span data-ttu-id="b3c28-p131">同样，在 **xsd:choice** 元素中声明的可选元素也经常存在问题。在以下简化的示例中，无从判断选项是曾经出现过一次但所具有的可选元素已不在此处，还是从未出现过。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p131">Similarly, optional elements declared in an **xsd:choice** element are usually problematic. In the following simplified example, there is no way to determine whether the choice occurred once with the optional element not being there or whether it never occurred at all.</span></span> 
  
```XML
<xsd:choice> 
    <xsd:element name="node" minOccurs="0"/> 
</xsd:choice> 

```

<span data-ttu-id="b3c28-p132">最后一个有问题的做法是使用无命名空间定义的 **xsd:any** 元素，就像在 `<xsd:any namespace="##other"/>` 元素后的  **** 中那样。此构造跟在可选元素后面时尤为麻烦。如果返回来看上一个示例，然后将最后一个节点改为 **xsd:any** 元素，就会看到与非确定性有关的所有以前的参数仍然适用，如下所示：</span><span class="sxs-lookup"><span data-stu-id="b3c28-p132">The final questionable practice is using an **xsd:any** element without a namespace definition, as in  `<xsd:any namespace="##other"/>` , after an **xsd:sequence** element. This construct is especially troublesome when it follows an optional element. If you revisit the previous example and change just the last node to an **xsd:any** element, you can see that all the previous arguments about nondeterminism still apply, as follows:</span></span> 
  
```XML
<xsd:element name="container"> 
    <xsd:complexType> 
        <xsd:sequence> 
            <xsd:element ref="aNode" /> 
            <xsd:element ref="anotherNode" minOccurs="0"/> 
            <xsd:any />     
        </xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

## <a name="illegal-enumeration-values"></a><span data-ttu-id="b3c28-234">非法枚举值</span><span class="sxs-lookup"><span data-stu-id="b3c28-234">Illegal Enumeration Values</span></span>

<span data-ttu-id="b3c28-p133">在您验证实际的实例文档之前，XSD 架构通常不会执行任何类型验证，但架构中存在枚举时例外。在这种情况下，架构会根据枚举类型来验证枚举值，以确保其为正确的节点值。以下是两个示例：</span><span class="sxs-lookup"><span data-stu-id="b3c28-p133">XSD schemas typically do not perform any type validation until you validate an actual instance document. An exception to this is when you have an enumeration in your schema. In this case, the schema validates the enumeration values against the enumeration types to ensure they are proper node values. Here are two examples:</span></span>
  
```XML
<xsd:simpleType name="showTimes"> 
    <xsd:restriction base="xsd:time"> 
        <xsd:enumeration value="18:30:00"/> 
        <xsd:enumeration value="20:45:00"/> 
        <xsd:enumeration value="eleven o'clock"/> 
    </xsd:restriction> 
</xsd:simpleType> 

```

<span data-ttu-id="b3c28-239">该架构无效，因为"eleven o'clock"对于类型为 **xsd:time** 的元素而言是无效值。</span><span class="sxs-lookup"><span data-stu-id="b3c28-239">This schema is invalid because "eleven o'clock" is not a valid value for an element of type **xsd:time**.</span></span>
  
<span data-ttu-id="b3c28-240">以下是一个更复杂的示例：</span><span class="sxs-lookup"><span data-stu-id="b3c28-240">The following is a more complex example:</span></span>
  
```XML
<xsd:simpleType name="concession"> 
    <xsd:restriction base="xsd:NMTOKEN"> 
        <xsd:enumeration value="GummyBears"/> 
        <xsd:enumeration value="SnowCaps"/> 
        <xsd:enumeration value="M&Ms"/> 
    </xsd:restriction> 
</xsd:simpleType> 

```

<span data-ttu-id="b3c28-p134">为了理解此示例为什么无效，必须了解类型 **xsd:NMTOKEN** 是如何定义的。W3C 数据类型规范是这样定义 **NMTOKEN** 类型的："NMTOKEN（名称标记）是名称字符的任意混合"。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p134">To understand why this example is invalid, you must understand how the type **xsd:NMTOKEN** is defined. The W3C data types specification defines the **NMTOKEN** type as follows: "An NMTOKEN (name token) is any mixture of name characters."</span></span> 
  
<span data-ttu-id="b3c28-243">如果进一步研究，你会发现“&”并非有效的名称字符，因此，“M&Ms”未验证为 **NMTOKEN** 类型。</span><span class="sxs-lookup"><span data-stu-id="b3c28-243">If you investigate further, you find that '&' is not a valid name character, and therefore "M&Ms" does not validate as an **NMTOKEN** type.</span></span> 
  
## <a name="empty-sequence-or-choice-elements"></a><span data-ttu-id="b3c28-244">空的序列或选项元素</span><span class="sxs-lookup"><span data-stu-id="b3c28-244">Empty Sequence or Choice Elements</span></span>

<span data-ttu-id="b3c28-245">当架构声明中包含空的 **xsd:choice** 或 **xsd:sequence** 元素时，MSXML 有时会引发架构声明相关错误，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="b3c28-245">MSXML sometimes raises errors about schema declarations that contain empty **xsd:choice** or **xsd:sequence** elements, as shown in the following example.</span></span> 
  
```XML
<xsd:element name="emptyContainer"> 
    <xsd:complexType> 
        <xsd:choice /> 
    </xsd:complexType> 
</xsd:element> 

```

<span data-ttu-id="b3c28-246">删除空的  `<xsd:choice />` 标记应该可以解决此问题。</span><span class="sxs-lookup"><span data-stu-id="b3c28-246">Removing the empty  `<xsd:choice />` tag should resolve this problem.</span></span> 
  
## <a name="regular-expressions"></a><span data-ttu-id="b3c28-247">正则表达式</span><span class="sxs-lookup"><span data-stu-id="b3c28-247">Regular Expressions</span></span>

<span data-ttu-id="b3c28-p135">MSXML 5.0 在加载正则表达式模式期间对其进行验证时可能会遇到问题。正则表达式可能较为复杂，在使用时一定要小心。每个 XSD 分析程序似乎都具有灵活的正则表达式语言。也就是说，它们既实施官方的 XSD 正则表达式语言，又实施来自其他正则表达式语言的元素。如果 InfoPath 表单设计器在分析正则表达式时遇到问题，则说明 InfoPath 生成的示例数据可能是无效的，或者根本没有生成数据。在设计阶段，这种情况是可以接受的，因为 InfoPath 只将示例数据用于格式设置。但是，如果您使用 MSXML 不支持的正则表达式，则当用户填写表单时，InfoPath 将无法根据该表达式验证值。[XML 架构部分 0：入门指南第二版](http://www.w3.org/TR/xmlschema-0/)描述了 XSD 正则表达式支持的内容。有关 XSD 正则表达式和 Unicode 第 1 级正则表达式的详细信息，请参阅 [Unicode 正则表达式（该链接可能指向英文页面）](http://www.unicode.org/reports/tr18/)。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p135">MSXML 5.0 can have problems validating regular expression patterns on load. Regular expressions can be complicated, and you should be careful when you are using them. Every XSD parser seems to have flexible regular expression languages; that is, they implement the official XSD regular expression language plus elements from other regular expression languages. If InfoPath form designer has problems parsing a regular expression, then the sample data InfoPath generates might be invalid or might not be generated at all. This is acceptable at design time, because InfoPath uses only sample data for formatting. However, if you use a regular expression that MSXML does not support, then InfoPath cannot validate a value against it when a user is filling out a form. [XML Schema Part 0: Primer Second Edition](http://www.w3.org/TR/xmlschema-0/)describes what is supported in XSD regular expressions. For more information about XSD regular expressions and Unicode level 1 regular expressions, see [Unicode Regular Expressions](http://www.unicode.org/reports/tr18/) .</span></span> 
  
## <a name="targetnamespace-attribute-issues"></a><span data-ttu-id="b3c28-256">targetNamespace 属性问题</span><span class="sxs-lookup"><span data-stu-id="b3c28-256">targetNamespace Attribute Issues</span></span>

<span data-ttu-id="b3c28-p136">XSD 的有趣之处在于：默认情况下， **targetNamespace** 属性只引用顶级声明。不过您可以设置  `attributeFormDefault=qualified` 和  `elementFormDefault=qualified` 来重写这种默认行为。举例来讲，假定您具有以下 XSD。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p136">XSD is interesting in that, by default, the **targetNamespace** attribute refers to only the top-level declarations, although you can set  `attributeFormDefault=qualified` and  `elementFormDefault=qualified` to override this default behavior. As an example, assume that you have the following XSD.</span></span> 
  
```XML
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns" > 
    <xsd:element name="root"> 
        <xsd:complexType> 
            <xsd:sequence> 
                <xsd:element name="local"/> 
            </xsd:sequence> 
        </xsd:complexType> 
    </xsd:element> 
</xsd:schema> 

```

<span data-ttu-id="b3c28-259">并且，您的 XML 实例文档类似以下示例。</span><span class="sxs-lookup"><span data-stu-id="b3c28-259">And that, your XML instance document resembles the following example.</span></span>
  
```XML
<ns:root xmlns:ns="http://ns"> 
    <local/> 
</ns:root> 

```

<span data-ttu-id="b3c28-p137">由于默认情况下，限定是关闭的，因此局部定义不需要目标命名空间。但是，如果将局部定义改为全局定义，则必须使用命名空间前缀限定引用。例如，以下架构是无效的。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p137">Local definitions do not require the target namespace because qualification is turned off by default. However, if you change your local definition to be global, then your reference must be qualified with the namespace prefix. For example, the following schema is invalid.</span></span>
  
```XML
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns" > 
    <xsd:element name="root"> 
        <xsd:complexType> 
            <xsd:sequence> 
                <xsd:element ref="global"/> 
            </xsd:sequence> 
        </xsd:complexType> 
    </xsd:element> 
 
    <xsd:element name="global"/> 
</xsd:schema> 

```

<span data-ttu-id="b3c28-p138">此架构无效的原因是命名空间"http://ns"中存在"global"字样。由于默认命名空间不是"http://ns"，所以无法识别简单的 ref="global"。若要修正此问题，必须为目标命名空间添加一个前缀，并将其用于所有全局引用和类型使用。纠正后的架构应如下所示：</span><span class="sxs-lookup"><span data-stu-id="b3c28-p138">This schema is invalid because "global" is in the namespace "http://ns". The simple ref="global" is not recognized because the default namespace is not "http://ns". To fix this, you must add a prefix for the target namespace and use that for all global references and type uses. The corrected schema looks like the following.</span></span>
  
```XML
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
    xmlns:ns="http://ns" targetNamespace="http://ns" > 
    <xsd:element name="root"> 
        <xsd:complexType> 
            <xsd:sequence> 
                <xsd:element ref="ns:global"/> 
            </xsd:sequence> 
        </xsd:complexType> 
    </xsd:element> 
 
    <xsd:element name="global"/> 
</xsd:schema> 

```

<span data-ttu-id="b3c28-267">如果您的架构指定了 **targetNamespace** 属性，应确保使用正确的命名空间前缀限定所有全局引用。</span><span class="sxs-lookup"><span data-stu-id="b3c28-267">If your schema has the **targetNamespace** attribute specified, ensure that all global references are qualified with the correct namespace prefix.</span></span> 
  
## <a name="xml-processing-instruction-encoding-unicode-vs-ansii"></a><span data-ttu-id="b3c28-268">XML 处理指令编码（Unicode 与 ANSII）</span><span class="sxs-lookup"><span data-stu-id="b3c28-268">XML Processing Instruction Encoding (Unicode vs. ANSII)</span></span>

<span data-ttu-id="b3c28-p139">XML 仅支持 Unicode 字符集。因此，如果保存采用 ANSII 字符的文件，则可能会丢失信息。但是，将文件另存为 UTF-16，对您的特殊用途而言可能又显得多余。为了降低 XML 读者的实施成本，XML 编写人员必须指出他们在顶级 XML 处理指令中使用了哪种编码。您或许认识以下处理指令。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p139">XML supports only Unicode character sets. Therefore, you may lose information if you save files that use ANSII characters. However, saving files as UTF-16 may be excessive for your particular use. To reduce the implementation cost of an XML reader, the XML author must state which encoding they are using in the top-level XML processing instruction. You may recognize the following processing instruction.</span></span>
  
```XML
xml version="1.0" encoding="UTF-8"
```

<span data-ttu-id="b3c28-p140">此处理指令标记指定文件的编码为 UTF-8。必须确保文件编码与处理指令标记中声明的编码相同，可以通过查看文件的字节数和 Unicode 字节顺序标记来确定编码。但还有一种更简单的方法。如果您在打开 XSD 架构时遇到问题，请将编码指定为“UTF-8”，在文本编辑器（如记事本）中打开它，然后使用 UTF-8 编码保存文件（记事本在“另存为”**** 对话框中提供了“编码”**** 下拉列表）。如果在打开文件时仍遇到问题，则说明不是编码问题。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p140">This processing instruction tag specifies that the encoding of the file is UTF-8. You must ensure that the file encoding is the same as the encoding stated in the processing instruction tag. You can determine the encoding by looking at the bytes of the file and looking for the Unicode byte order marks. But there is an easier way. If you have problems opening an XSD schema, specify the encoding as "UTF-8", open it in a text editor such as Notepad, and then save the file by using UTF-8 encoding (Notepad provides the **Encoding** drop-down list in the **Save As** dialog box). If you still have problems opening the file, it is not an encoding issue.</span></span> 
  
## <a name="maxoccurs-attribute-inside-the-xsdall-element"></a><span data-ttu-id="b3c28-280">xsd:all 元素内的 maxOccurs 属性</span><span class="sxs-lookup"><span data-stu-id="b3c28-280">maxOccurs Attribute Inside the xsd:all Element</span></span>

<span data-ttu-id="b3c28-p141">因 XML 架构建议中对非确定性进行定义的方式所致，对于 **xsd:all** 元素内的 **xsd:element** 元素而言，其 **maxOccurs** 属性的唯一有效值为 1。例如，以下构造有效：</span><span class="sxs-lookup"><span data-stu-id="b3c28-p141">Due to the way nondeterminism is defined in the XML Schema recommendation, the only valid value for the **maxOccurs** attribute of an **xsd:element** element inside an **xsd:all** element is 1. For example, the following is valid.</span></span> 
  
```XML
<xsd:all> 
    <xsd:element name="x" minOccurs="0"/> 
    <xsd:element name="docs" minOccurs="0"/> 
</xsd:all> 

```

<span data-ttu-id="b3c28-283">但是，以下示例无效：</span><span class="sxs-lookup"><span data-stu-id="b3c28-283">However, this example is not valid.</span></span>
  
```XML
<xsd:all>     
    <xsd:element name="x" minOccurs="0" maxOccurs="unbounded"/> 
    <xsd:element name="docs" minOccurs="0" maxOccurs="unbounded"/> 
</xsd:all> 

```

<span data-ttu-id="b3c28-p142">此示例无效的原因是验证系统无法确定两次出现的  `<x/>` 是同时映射到一个声明，还是一个映射到声明，另一个映射到其他无效定义。同一行中的一个  `<xsd:all>` 标记内不能放置两个同名元素。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p142">This example is invalid because the validation system cannot determine whether two occurrences of  `<x/>` map to the single declaration or to the declaration and another invalid definition. Along the same lines, you cannot have two elements of the same name in an  `<xsd:all>` tag.</span></span> 
  
<span data-ttu-id="b3c28-p143">此示例也很有意思，因为它允许您在一个包含元素中以任意顺序使用任意数量的  `<x/>` 和  `<docs/>` 节点。尽管此构造无效，但提供了一个变通办法。通过使用 **xsd:choice** 元素，可以得到同样的结果，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p143">This example is also interesting because it allows you to have any number of  `<x/>` and  `<docs/>` nodes inside a containing element in any order. Although this construct is invalid, there is a workaround. By using the **xsd:choice** element, you can achieve the same result, as demonstrated in the following example.</span></span> 
  
```XML
<xsd:choice minOccurs="0" maxOccurs="unbounded"> 
    <xsd:element name="x" /> 
    <xsd:element name="docs" /> 
</xsd:choice> 

```

## <a name="how-to-edit-or-author-an-xsd-for-infopath"></a><span data-ttu-id="b3c28-289">如何为 InfoPath 编辑或编写 XSD</span><span class="sxs-lookup"><span data-stu-id="b3c28-289">How to Edit or Author an XSD for InfoPath</span></span>

<span data-ttu-id="b3c28-290">以下部分给出两个示例，演示如何编辑或编写架构，以在 InfoPath 中产生特定效果。</span><span class="sxs-lookup"><span data-stu-id="b3c28-290">The two examples in the following sections show how to edit or author a schema to produce specific results in InfoPath.</span></span>
  
## <a name="allowing-user-defined-elements-to-be-inserted-in-the-fields-task-pane"></a><span data-ttu-id="b3c28-291">允许将用户定义的元素插入"域"任务窗格</span><span class="sxs-lookup"><span data-stu-id="b3c28-291">Allowing User-defined Elements to Be Inserted in the Fields Task Pane</span></span>

<span data-ttu-id="b3c28-292">要允许用户定义的元素显示在“域”**** 任务窗格中的父元素下，必须在父元素下插入 **xsd:any** 元素。</span><span class="sxs-lookup"><span data-stu-id="b3c28-292">To allow user-defined elements to appear under a parent element in the **Fields** task pane, you must insert an **xsd:any** element under the parent element.</span></span> <span data-ttu-id="b3c28-293">要允许用户定义的元素插入到 `<your_node_name>` 中，XSD 声明应类似如下。</span><span class="sxs-lookup"><span data-stu-id="b3c28-293">To allow user-defined elements to be inserted inside  `<your_node_name>` , the XSD declaration should resemble the following.</span></span> 
  
```XML
<xsd:element name="your_node_name"> 
    <xsd:complexType> 
        <xsd:sequence> 
            <xsd:any namespace="##any | ##other"  
                minOccurs="0" maxOccurs="unbounded"/> 
        </xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

<span data-ttu-id="b3c28-294">如果还要允许用户定义的属性，则必须将  `<xsd:anyAttribute namespace="##any | ##other"/>` 添加到元素声明中。</span><span class="sxs-lookup"><span data-stu-id="b3c28-294">If you also want to allow user-defined attributes, then you must add  `<xsd:anyAttribute namespace="##any | ##other"/>` to the element declaration.</span></span> 
  
## <a name="allowing-rich-text-elements-to-be-bound-in-infopath-design-and-edit-modes"></a><span data-ttu-id="b3c28-295">允许在 InfoPath 设计和编辑模式中绑定格式文本元素</span><span class="sxs-lookup"><span data-stu-id="b3c28-295">Allowing Rich Text Elements to be Bound in InfoPath Design and Edit Modes</span></span>

<span data-ttu-id="b3c28-296">如果需要声明一个可绑定到 **Rich Text Box**控件的元素，则应具有以下表单，其中包括 **xsd:any** 元素，该元素的命名空间属性设置为"http://www.w3.org/1999/xhtml"，如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="b3c28-296">If you want to declare an element that can be bound to a **Rich Text Box** control, then it should have the following form, which includes the **xsd:any** element that has a namespace attribute set to "http://www.w3.org/1999/xhtml" as shown in the following example.</span></span> 
  
```XML
<xsd:element name="your_node_name"> 
    <xsd:complexType mixed="true"> 
        <xsd:sequence> 
            <xsd:any namespace="http://www.w3.org/1999/xhtml"  
                minOccurs="0" maxOccurs="unbounded"/> 
        </xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

## <a name="conclusion"></a><span data-ttu-id="b3c28-297">结论</span><span class="sxs-lookup"><span data-stu-id="b3c28-297">Conclusion</span></span>

<span data-ttu-id="b3c28-p145">InfoPath 支持基于外部编写的 XML 架构 (.xsd) 文件设计 XML 表单解决方案。利用这种支持，您可以创建使用行业标准架构的表单模板，也可以创建使用贵公司/组织创建的自定义架构的表单模板。借助本文中提供的信息，您还可以创建与 InfoPath 兼容的自定义 XSD 架构文件，并且可以解决在将外部编写的 XSD 文件加载到 InfoPath 设计环境时可能遇到的常见问题。</span><span class="sxs-lookup"><span data-stu-id="b3c28-p145">By taking advantage of InfoPath support for designing XML form solutions that are based on externally authored XML Schema (.xsd) files, you can create a form template that works with an industry-standard schema or custom schema created by your company or organization. By using the information in this article, you can create custom XSD schema files that are compatible with InfoPath, and you can troubleshoot common issues that you may encounter when you load externally authored XSD files into the InfoPath design environment.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b3c28-300">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b3c28-300">See also</span></span>

- [<span data-ttu-id="b3c28-301">W3C XML 架构</span><span class="sxs-lookup"><span data-stu-id="b3c28-301">W3C XML Schema</span></span>](http://www.w3.org/XML/Schema)
- [<span data-ttu-id="b3c28-302">W3C XML 架构入门指南</span><span class="sxs-lookup"><span data-stu-id="b3c28-302">W3C XML Schema Primer</span></span>](http://www.w3.org/TR/xmlschema-0/)
- [<span data-ttu-id="b3c28-303">W3C XML 架构结构参考（该链接可能指向英文页面）</span><span class="sxs-lookup"><span data-stu-id="b3c28-303">W3C XML Schema Structures Reference</span></span>](https://www.xml.com/pub/a/2000/11/29/schemas/structuresref.html)
- [<span data-ttu-id="b3c28-304">W3C XML 架构数据类型参考（该链接可能指向英文页面）</span><span class="sxs-lookup"><span data-stu-id="b3c28-304">W3C XML Schema Datatypes Reference</span></span>](https://www.xml.com/pub/a/2000/11/29/schemas/dataref.html)
- [<span data-ttu-id="b3c28-305">XML 架构教程（该链接可能指向英文页面）</span><span class="sxs-lookup"><span data-stu-id="b3c28-305">XML Schema Tutorial</span></span>](https://www.w3schools.com/xml/schema_intro.asp)
- [<span data-ttu-id="b3c28-306">XML 开发人员中心</span><span class="sxs-lookup"><span data-stu-id="b3c28-306">XML Developer Center</span></span>](http://msdn.microsoft.com/en-us/xml/default.aspx)

