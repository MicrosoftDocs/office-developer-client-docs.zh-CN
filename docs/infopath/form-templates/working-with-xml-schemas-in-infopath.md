---
title: 在 InfoPath 中使用 XML 架构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: c1d70e9f-b9fc-7bdb-107e-d0cd8191607b
description: 使用 Microsoft InfoPath 创建的表单模板可以通过 XML 架构 (XSD)，对从 InfoPath 表单输入、编辑和输出的 XML 执行结构和数据验证。在 InfoPath 表单设计器中创建的每个表单模板都至少包含一个 XSD 架构文件 (.xsd)，该架构文件用于在运行时进行验证。
ms.openlocfilehash: 25828c3ec21d22a9952452d5a82fe1a3b4bab54c
ms.sourcegitcommit: ef717c65d8dd41ababffb01eafc443c79950aed4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25395502"
---
# <a name="working-with-xml-schemas-in-infopath"></a>在 InfoPath 中使用 XML 架构

使用 Microsoft InfoPath 创建的表单模板可以通过 XML 架构 (XSD)，对从 InfoPath 表单输入、编辑和输出的 XML 执行结构和数据验证。在 InfoPath 表单设计器中创建的每个表单模板都至少包含一个 XSD 架构文件 (.xsd)，该架构文件用于在运行时进行验证。
  
> [!NOTE]
> 本主题中包含的信息适用于为在 InfoPath 编辑器中使用而设计的表单模板。浏览器兼容的表单模板具有更为严格的 XSD 架构要求。有关详细信息，请参阅 MSDN 上提供的有关浏览器兼容的表单模板中的 XML 架构的文档。 
  
## <a name="using-externally-authored-xml-schemas"></a>使用外部编写的 XML 架构

若要加载在 InfoPath 以外编写的 XSD 架构文件，请执行下列步骤。
  
### <a name="to-create-a-form-template-based-on-an-external-schema"></a>基于外部架构创建表单模板

1. 在 Backstage 中，单击“新建”****，在“高级表单模板”**** 下单击“XML 或架构”****，然后单击“设计此表单”****。
    
2. 在“数据源向导”**** 中，指定要使用的 XSD 架构文件，然后单击“下一步”**** 并完成向导的其余页面。 
    
## <a name="unsupported-xsd-constructs"></a>不受支持的 XSD 构造

以下部分描述了 InfoPath 在运行时无法处理的 XSD 构造。在 InfoPath 表单设计器中创建表单模板时，应避免使用这些构造。
  
## <a name="entity-and-entities-types"></a>ENTITY 和 ENTITIES 类型

**ENTITY** 和 **ENTITIES** 类型需要文档类型定义 (DTD) 来进行验证，而 InfoPath 不支持 DTD。InfoPath 不允许根据这种架构设计表单模板，并且会显示一条错误消息，建议您将 **ENTITY** 类型改为 **NCName** 类型（ **ENTITY** 派生自该类型）。 
  
> [!NOTE]
>  如果您在设计模式之外手动编写了一个 InfoPath 表单模板，并且该表单模板使用了包括 **ENTITY** 和 **ENTITIES** 类型的 XSD，当 Template.xml 文件包含这些类型所必需的 DTD 时，该 InfoPath 表单模板在运行时或许可以工作。 
  
## <a name="required-xsdany-element"></a>必需的 xsd:any 元素

如果存在 **xsd:any** 通配符元素，即存在 **minOccurs** 属性值大于零（“required any”）的 **xsd:any** 元素，则会明确阻止 InfoPath 创建此架构片段的有效实例。InfoPath 必须能够创建此架构片段的有效实例，才能生成使用此架构片段的表单。在运行“数据源向导”**** 的过程中，包含必需的 **xsd:any** 元素的架构要求您选择要使用的架构元素，以代替必需的 **xsd:any** 元素。 
  
## <a name="elements-with-an-abstract-complex-type"></a>具有抽象复杂类型的元素

InfoPath 设计模式支持根据使用抽象复杂类型的架构设计表单模板。例如，如果一个名为  `shippingAddress` 的元素有一个名为  `address` 的抽象复杂类型，该类型具有两个派生类型：  `USAddress` 和  `CanadianAddress`，则 InfoPath 会将  `shippingAddress` 的任意实例视为在以下二者间进行选择：类型为  `shippingAddress` 的  `USAddress` 或类型为  `shippingAddress` 的  `CanadianAddress`。在本例中，如果提供的架构不包含从地址派生的类型，则 InfoPath 会请求另一个满足此要求的架构。 
  
## <a name="xsd-constructs-with-reduced-functionality"></a>具有缩简功能的 XSD 构造

以下部分描述的 XSD 构造用于在 InfoPath 表单设计器中创建表单模板时，功能有所缩减。
  
## <a name="substitution-groups"></a>替换组

替换组的所有成员都显示在“域”**** 任务窗格中。InfoPath 将可能的替换项表示为所有替换组中的一个选项（不是抽象元素的定义元素也包括在内）。如果某个抽象元素没有替换组，则 InfoPath 会提示您提供一个架构，其中至少包含一个作为替换组的元素。 
  
## <a name="unbounded-choice-elements"></a>无限次选项元素

以下架构片段显示了一个无限次选项元素：
  
```XML
<xsd:choice maxOccurs="unbounded"> 
    <xsd:element name="my_element_1"/> 
    <xsd:element name="my_element_2"/> 
</xsd:choice> 

```

InfoPath 将重复选项元素作为重复选项显示在“域”**** 任务窗格中。这里有一个“重复选项组”**** 控件，可以用来表示由 XSD 中的重复选项元素所定义的异类列表。 
  
## <a name="repeating-sequence"></a>重复序列

以下架构片段显示了一个重复序列：
  
```XML
<xsd:sequence maxOccurs="unbounded"> 
    <xsd:element name="my_element_1"/> 
    <xsd:element name="my_element_2" minOccurs="0"/> 
</xsd:sequence> 

```

只要重复序列中包含必需的元素，InfoPath 就会不加修改地加载 XSD，并且允许您将重复节控件绑定到重复序列。
  
## <a name="choice-of-model-groups"></a>模型组选项

以下架构片段显示了包含若干模型组的选项元素：
  
```XML
<xsd:choice> 
    <xsd:element name="my_element_1"/> 
    <xsd:sequence> 
        <xsd:element name="my_element_2"/> 
        <xsd:element name="my_element_3"/> 
    </xsd:sequence> 
</xsd:choice> 

```

InfoPath 设计模式支持此类 XSD 构造，并且不要求表单设计人员做任何修改。尽管 InfoPath 不会修改架构的含义，但是它会将上述选项构造简化为“域”**** 任务窗格中折叠起来的单个对等选项。 
  
## <a name="optional-sibling-with-same-qualified-name"></a>具有相同限定名称的可选同级元素

以下架构片段显示了具有相同限定名称 (`QName`) 的可选同级元素：
  
```xml
<xsd:sequence> 
    <xsd:element name="my_element_1" minOccurs="0"/> 
    <xsd:element name="my_element_2"/> 
            <xsd:element name="my_element_1"/> 
</xsd:sequence> 

```

这些节点的 **XPath** 表达式可能非常复杂，原因是每个潜在的 XML 实例都必须包括在 InfoPath 表单设计器内。InfoPath 在为某些架构部分创建正确的 **XPath** 绑定时可能会遇到困难，因此它不会公开这些部分，而是显示有关这些被忽略的架构部分的警告。 
  
## <a name="xsd-constructs-with-special-meaning-in-infopath"></a>在 InfoPath 中具有特殊含义的 XSD 构造

以下部分描述的 XSD 构造用于在设计模式中创建表单模板时，有着特殊含义。这些部分描述了如何在架构中使用这些构造来实现特定的行为。
  
## <a name="adding-new-element-fields-and-groups-with-the-fields-task-pane"></a>使用"域"任务窗格添加新的元素域和组

您可以对架构进行设计，以便可以使用“域”**** 任务窗格，在设计时向元素中添加新的元素域和组。为此，需要使用通过 **##any** 通配符指定命名空间属性的、可选的无限次 **xsd:any** 元素在架构中声明一个元素。然后，在设计模式下，可以使用“域”**** 任务窗格将新的元素域和组添加到该元素中。例如，可以将新内容添加到以下元素中： 
  
```XML
<xsd:element name="open"> 
    <xsd:complexType> 
         <xsd:sequence> 
             <xsd:any minOccurs="0" maxOccurs="unbounded" namespace="##any"processContents="lax"/> 
         </xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

## <a name="adding-new-attribute-fields-with-the-fields-task-pane"></a>使用"域"任务窗格添加新的属性域

与元素的情况类似，您也可以使用将命名空间属性指定为 **##any** 通配符的 **anyAttribute** 元素来声明一个属性。在设计时，可以使用“域”**** 任务窗格将新的内容添加到该架构属性中。 
  
```XML
<xsd:element name="open"> 
    <xsd:complexType> 
        <xsd:anyAttribute namespace="##any" processContents="lax"/> 
    </xsd:complexType> 
</xsd:element> 

```

## <a name="storing-xml-signatures-in-the-data-source"></a>将 XML 签名存储在数据源中

若要使用户能够在运行时对表单进行数字签名，数据源的架构必须声明一个名为 signature 的元素，用于存储用户在对表单进行签名时所创建的 XML 签名（数字签名）信息。可以使用 **xsd:any** 元素来实现此声明，该元素将命名空间属性指定为带通配符的 XML 签名命名空间，例如"https://www.w3c.org/2000/09/xmldsig#"： 
  
```XML
<xsd:element name="signature"> 
    <xsd:complexType> 
        <xsd:sequence> 
            <xsd:any namespace="https://www.w3c.org/2000/09/xmldsig#"  
             processContents="lax" minOccurs="0" maxOccurs="unbounded"/> 
        <xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

## <a name="binding-a-field-to-a-rich-text-box-control"></a>将域绑定到格式文本框控件

 InfoPath 中的“格式文本框”**** 控件会生成通用 XHTML；因此，您的架构必须指定任意数量的文本和 XHTML 节点在表单实例的 XML 中都有效。可以使用以下 XSD 构造进行指定： 
  
```XML
<xsd:element name="xhtml"> 
    <xsd:complexType mixed="true"> 
        <xsd:sequence> 
            <xsd:any minOccurs="0" maxOccurs="unbounded" namespace="https://www.w3.org/1999/xhtml" processContents="lax"/> 
        </xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

> [!NOTE]
> InfoPath 从不修改架构文件 (.xsd) 的内容，但它可能会为了设计目的，从逻辑上推断架构文件的子集。无论在设计时还是在运行时，表单模板内的架构文件都始终保持不变。 
  
## <a name="debugging-common-xsd-errors"></a>调试常见 XSD 错误

如果您加载在外部编写的 XSD 文件，以便在 InfoPath 表单设计器中创建表单模板，则可能收到以下两种错误消息之一：MSXML 错误消息或 InfoPath 错误消息。MSXML 错误消息出现在 InfoPath 错误消息对话框的“详细信息”**** 部分，并且始终以引用正在引发此错误的架构文件的名称或路径开头。某些有效的 XSD 架构不受 InfoPath 支持；“不受支持的 XSD 构造”部分讨论了这些 XSD 构造。以下部分描述了一些会导致在 InfoPath 中无法成功加载架构的常见错误。 
  
## <a name="the-xsd-namespace-declaration"></a>XSD 命名空间声明

与所有 W3C 标准类似，XML 架构 (XSD) 在成为一项建议标准之前，也经历了漫长的评审过程，产生了大量的工作草案，因此，有很多 XSD 文件是基于这些逐渐完善的标准编写的。在此过程中，Microsoft 创建了一种称为"简化 XML 数据"(XDR) 的专有架构语言，该语言随 MSXML 3.0 提供。从发布 MSXML 4.0 开始，Microsoft XML Core Services 支持完整的 XSD 建议。很多用来创建架构的程序没有等到 XSD 变成一项完整建议，这些程序的旧版本可能创建了 InfoPath 所依赖的 MSXML 5.0 基础架构不支持的过时 XSD 文件。
  
为了确保 XSD 文件支持完整的 XSD 建议，XSD 文件应在 \<schema\> 标记中包含以下 XML 命名空间声明：
  
```XML
xmlns:xsd="https://www.w3.org/2001/XMLSchema"
```

与所有 XML 命名空间声明类似，XML 前缀（这里为"xsd"）可以是任何有效的前缀字符串。在实际操作中可能会看到的一些常用前缀有"xsd"、"xs"和""（无前缀）。如果缺少该命名空间声明，则 MSXML 通常会报告有关"根未正确定义"错误。
  
## <a name="importing-and-including-schemas"></a>导入和包含架构

XSD 架构可以扩展，并且可以导入和包含其他架构。一般而言，如果 **targetNamespace** 属性中指定的架构与当前架构不同，则应导入架构。如果 **targetNamespace** 属性中指定的架构与当前架构相同，则应包含架构。 
  
导入和包含架构的语义如下：
  
```XML
<xsd:import namespace = "[anyURI]" schemaLocation = "[anyURI]"/> 
<xsd:include schemaLocation = "[anyURI]"/> 

```

如果 **schemaLocation** 属性缺失（就像在某些转换器中那样），则 MSXML 会因找不到文件而引发错误。如果收到此错误，还应进行检查以确保表单模板的用户能够访问在 schemaLocation 属性中指定的资源或位置。很明显，如果 **schemaLocation** 属性引用的服务器或目录已关闭或不存在，或者用户无访问权限，就会发生错误。另外，一定要检查所有导入和包含的架构，以确保其有效。 
  
> [!NOTE]
> 仅当 InfoPath 首次导入架构，即您第一次基于现有架构开始设计表单时，因 **schemaLocation** 属性问题引发的错误才成为问题。此后，InfoPath 将使用存储在表单模板中的架构文件的缓存版本。 
  
在导入架构时，如果该架构没有指定 **targetNamespace** 属性，则允许使用空的命名空间属性。通常，导入时使用的命名空间必须与在要导入的架构中指定的 **targetNamespace** 相符。 
  
## <a name="nondeterministic-schemas"></a>非确定性架构

InfoPath 所依赖的 MSXML 5.0 基础结构会可靠地检测和引发错误，以提醒您注意非确定性架构，但生成的错误消息中不提供行号，因此您无从知道究竟是架构的哪一部分引发了错误。本节讨论的主题就是，为什么对于 XSD 架构文件而言确定性很重要，以及非确定性意味着什么。另外还显示一些应避免的常见错误。
  
XSD 架构存在的目的是为了验证 XML 数据结构和类型语义。为完成此任务，验证系统（这里为 MSXML 5.0）必须将 XML 节点映射到 XSD 声明。如果不进行这种映射，验证系统将无法完成其任务。如果能保证实现映射，则架构就是确定性的。如果有一个 XML 实例使这种映射无法实现，则架构就是非确定性的。
  
以下示例架构为非确定性的：
  
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

为了阐释此 XSD 片段为什么是非确定性的，在此假设您拥有以下 XML 片段，您要使用此架构对其进行验证：
  
```XML
<file_Information> 
    <file_name>my_Schema.xsd</file_name> 
    <file_path>c:\xsd</file_path> 
</file_Information> 

```

在此 XML 片段中，没有指明  *\<file_path\>*  元素是来自选项声明第一部分的必需节点，还是来自选项声明第二部分的可选节点。这种区分非常重要，原因如下： 
  
1. 如果根据选项声明的第一部分验证 XML 片段，则 XML 对于架构有效。
    
2. 如果根据选项声明的第二部分验证 XML 片段，则因为缺少必需的 \<URI\> 节点，架构无效。 
    
因为存在有效路径，所以有些 XSD 验证系统在针对此架构进行验证时会发生错误。MSXML 更为严格，它会引发一个错误，指明架构为非确定性架构。
  
下面再给出几个非确定性架构的示例。第一个示例涉及可选元素。这些情况通常源于 XDR 到 XSD 转换器，因为这两种架构语言的默认基数不同。要考虑的第一种情况是使用 **xsd:choice** 和 **xsd:sequence** 元素声明的可选元素。对于在 **xsd:sequence** 元素中声明的可选元素，只要同名元素的出现次数不超过一次，并且中间只有可选元素，通常就能够正确验证这些可选元素。例如： 
  
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

为了理解此架构片段为什么是非确定性的，在此假设您拥有以下无效 XML 片段：
  
```XML
<container> 
    <aNode/> 
    <aNode/> 
    <anotherNode/> 
</container> 

```

观察此片段，您会看出它为什么是无效的： `<aNode>` 元素前面有两个  `<anotherNode>` 元素，但实际上只允许有一个。 
  
现在假设您具有以下要验证的 XML 实例：
  
```XML
<container> 
    <aNode/> 
    <aNode/> 
</container> 

```

难点在于判断该实例是否有效。您是拥有两个  `<aNode>` 元素，但只允许其中之一？还是两个  `<aNode>` 元素都允许？无从知道答案，因此该架构是非确定性的。 
  
同样，在 **xsd:choice** 元素中声明的可选元素也经常存在问题。在以下简化的示例中，无从判断选项是曾经出现过一次但所具有的可选元素已不在此处，还是从未出现过。 
  
```XML
<xsd:choice> 
    <xsd:element name="node" minOccurs="0"/> 
</xsd:choice> 

```

最后一个有问题的做法是使用无命名空间定义的 **xsd:any** 元素，就像在 `<xsd:any namespace="##other"/>` 元素后的  **** 中那样。此构造跟在可选元素后面时尤为麻烦。如果返回来看上一个示例，然后将最后一个节点改为 **xsd:any** 元素，就会看到与非确定性有关的所有以前的参数仍然适用，如下所示： 
  
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

## <a name="illegal-enumeration-values"></a>非法枚举值

在您验证实际的实例文档之前，XSD 架构通常不会执行任何类型验证，但架构中存在枚举时例外。在这种情况下，架构会根据枚举类型来验证枚举值，以确保其为正确的节点值。以下是两个示例：
  
```XML
<xsd:simpleType name="showTimes"> 
    <xsd:restriction base="xsd:time"> 
        <xsd:enumeration value="18:30:00"/> 
        <xsd:enumeration value="20:45:00"/> 
        <xsd:enumeration value="eleven o'clock"/> 
    </xsd:restriction> 
</xsd:simpleType> 

```

该架构无效，因为"eleven o'clock"对于类型为 **xsd:time** 的元素而言是无效值。
  
以下是一个更复杂的示例：
  
```XML
<xsd:simpleType name="concession"> 
    <xsd:restriction base="xsd:NMTOKEN"> 
        <xsd:enumeration value="GummyBears"/> 
        <xsd:enumeration value="SnowCaps"/> 
        <xsd:enumeration value="M&Ms"/> 
    </xsd:restriction> 
</xsd:simpleType> 

```

为了理解此示例为什么无效，必须了解类型 **xsd:NMTOKEN** 是如何定义的。W3C 数据类型规范是这样定义 **NMTOKEN** 类型的："NMTOKEN（名称标记）是名称字符的任意混合"。 
  
如果进一步研究，你会发现“&”并非有效的名称字符，因此，“M&Ms”未验证为 **NMTOKEN** 类型。 
  
## <a name="empty-sequence-or-choice-elements"></a>空的序列或选项元素

当架构声明中包含空的 **xsd:choice** 或 **xsd:sequence** 元素时，MSXML 有时会引发架构声明相关错误，如下例所示。 
  
```XML
<xsd:element name="emptyContainer"> 
    <xsd:complexType> 
        <xsd:choice /> 
    </xsd:complexType> 
</xsd:element> 

```

删除空的  `<xsd:choice />` 标记应该可以解决此问题。 
  
## <a name="regular-expressions"></a>正则表达式

MSXML 5.0 在加载正则表达式模式期间对其进行验证时可能会遇到问题。正则表达式可能较为复杂，在使用时一定要小心。每个 XSD 分析程序似乎都具有灵活的正则表达式语言。也就是说，它们既实施官方的 XSD 正则表达式语言，又实施来自其他正则表达式语言的元素。如果 InfoPath 表单设计器在分析正则表达式时遇到问题，则说明 InfoPath 生成的示例数据可能是无效的，或者根本没有生成数据。在设计阶段，这种情况是可以接受的，因为 InfoPath 只将示例数据用于格式设置。但是，如果您使用 MSXML 不支持的正则表达式，则当用户填写表单时，InfoPath 将无法根据该表达式验证值。[XML 架构部分 0：入门指南第二版](https://www.w3.org/TR/xmlschema-0/)描述了 XSD 正则表达式支持的内容。有关 XSD 正则表达式和 Unicode 第 1 级正则表达式的详细信息，请参阅 [Unicode 正则表达式（该链接可能指向英文页面）](https://www.unicode.org/reports/tr18/)。 
  
## <a name="targetnamespace-attribute-issues"></a>targetNamespace 属性问题

XSD 的有趣之处在于：默认情况下， **targetNamespace** 属性只引用顶级声明。不过您可以设置  `attributeFormDefault=qualified` 和  `elementFormDefault=qualified` 来重写这种默认行为。举例来讲，假定您具有以下 XSD。 
  
```XML
<xsd:schema xmlns:xsd="https://www.w3.org/2001/XMLSchema" targetNamespace="https://ns" > 
    <xsd:element name="root"> 
        <xsd:complexType> 
            <xsd:sequence> 
                <xsd:element name="local"/> 
            </xsd:sequence> 
        </xsd:complexType> 
    </xsd:element> 
</xsd:schema> 

```

并且，您的 XML 实例文档类似以下示例。
  
```XML
<ns:root xmlns:ns="https://ns"> 
    <local/> 
</ns:root> 

```

由于默认情况下，限定是关闭的，因此局部定义不需要目标命名空间。但是，如果将局部定义改为全局定义，则必须使用命名空间前缀限定引用。例如，以下架构是无效的。
  
```XML
<xsd:schema xmlns:xsd="https://www.w3.org/2001/XMLSchema" targetNamespace="https://ns" > 
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

此架构无效的原因是命名空间"https://ns"中存在"global"字样。由于默认命名空间不是"https://ns"，所以无法识别简单的 ref="global"。若要修正此问题，必须为目标命名空间添加一个前缀，并将其用于所有全局引用和类型使用。纠正后的架构应如下所示：
  
```XML
<xsd:schema xmlns:xsd="https://www.w3.org/2001/XMLSchema"  
    xmlns:ns="https://ns" targetNamespace="https://ns" > 
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

如果您的架构指定了 **targetNamespace** 属性，应确保使用正确的命名空间前缀限定所有全局引用。 
  
## <a name="xml-processing-instruction-encoding-unicode-vs-ansii"></a>XML 处理指令编码（Unicode 与 ANSII）

XML 仅支持 Unicode 字符集。因此，如果保存采用 ANSII 字符的文件，则可能会丢失信息。但是，将文件另存为 UTF-16，对您的特殊用途而言可能又显得多余。为了降低 XML 读者的实施成本，XML 编写人员必须指出他们在顶级 XML 处理指令中使用了哪种编码。您或许认识以下处理指令。
  
```XML
xml version="1.0" encoding="UTF-8"
```

此处理指令标记指定文件的编码为 UTF-8。必须确保文件编码与处理指令标记中声明的编码相同，可以通过查看文件的字节数和 Unicode 字节顺序标记来确定编码。但还有一种更简单的方法。如果您在打开 XSD 架构时遇到问题，请将编码指定为“UTF-8”，在文本编辑器（如记事本）中打开它，然后使用 UTF-8 编码保存文件（记事本在“另存为”**** 对话框中提供了“编码”**** 下拉列表）。如果在打开文件时仍遇到问题，则说明不是编码问题。 
  
## <a name="maxoccurs-attribute-inside-the-xsdall-element"></a>xsd:all 元素内的 maxOccurs 属性

因 XML 架构建议中对非确定性进行定义的方式所致，对于 **xsd:all** 元素内的 **xsd:element** 元素而言，其 **maxOccurs** 属性的唯一有效值为 1。例如，以下构造有效： 
  
```XML
<xsd:all> 
    <xsd:element name="x" minOccurs="0"/> 
    <xsd:element name="docs" minOccurs="0"/> 
</xsd:all> 

```

但是，以下示例无效：
  
```XML
<xsd:all>     
    <xsd:element name="x" minOccurs="0" maxOccurs="unbounded"/> 
    <xsd:element name="docs" minOccurs="0" maxOccurs="unbounded"/> 
</xsd:all> 

```

此示例无效的原因是验证系统无法确定两次出现的  `<x/>` 是同时映射到一个声明，还是一个映射到声明，另一个映射到其他无效定义。同一行中的一个  `<xsd:all>` 标记内不能放置两个同名元素。 
  
此示例也很有意思，因为它允许您在一个包含元素中以任意顺序使用任意数量的  `<x/>` 和  `<docs/>` 节点。尽管此构造无效，但提供了一个变通办法。通过使用 **xsd:choice** 元素，可以得到同样的结果，如以下示例所示。 
  
```XML
<xsd:choice minOccurs="0" maxOccurs="unbounded"> 
    <xsd:element name="x" /> 
    <xsd:element name="docs" /> 
</xsd:choice> 

```

## <a name="how-to-edit-or-author-an-xsd-for-infopath"></a>如何为 InfoPath 编辑或编写 XSD

以下部分给出两个示例，演示如何编辑或编写架构，以在 InfoPath 中产生特定效果。
  
## <a name="allowing-user-defined-elements-to-be-inserted-in-the-fields-task-pane"></a>允许将用户定义的元素插入"域"任务窗格

要允许用户定义的元素显示在“域”**** 任务窗格中的父元素下，必须在父元素下插入 **xsd:any** 元素。 要允许用户定义的元素插入到 `<your_node_name>` 中，XSD 声明应类似如下。 
  
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

如果还要允许用户定义的属性，则必须将  `<xsd:anyAttribute namespace="##any | ##other"/>` 添加到元素声明中。 
  
## <a name="allowing-rich-text-elements-to-be-bound-in-infopath-design-and-edit-modes"></a>允许在 InfoPath 设计和编辑模式中绑定格式文本元素

如果需要声明一个可绑定到 **Rich Text Box**控件的元素，则应具有以下表单，其中包括 **xsd:any** 元素，该元素的命名空间属性设置为"https://www.w3.org/1999/xhtml"，如以下示例所示。 
  
```XML
<xsd:element name="your_node_name"> 
    <xsd:complexType mixed="true"> 
        <xsd:sequence> 
            <xsd:any namespace="https://www.w3.org/1999/xhtml"  
                minOccurs="0" maxOccurs="unbounded"/> 
        </xsd:sequence> 
    </xsd:complexType> 
</xsd:element> 

```

## <a name="conclusion"></a>结论

InfoPath 支持基于外部编写的 XML 架构 (.xsd) 文件设计 XML 表单解决方案。利用这种支持，您可以创建使用行业标准架构的表单模板，也可以创建使用贵公司/组织创建的自定义架构的表单模板。借助本文中提供的信息，您还可以创建与 InfoPath 兼容的自定义 XSD 架构文件，并且可以解决在将外部编写的 XSD 文件加载到 InfoPath 设计环境时可能遇到的常见问题。
  
## <a name="see-also"></a>另请参阅

- [W3C XML 架构](https://www.w3.org/XML/Schema)
- [W3C XML 架构入门指南](https://www.w3.org/TR/xmlschema-0/)
- [W3C XML 架构结构参考（该链接可能指向英文页面）](https://www.xml.com/pub/a/2000/11/29/schemas/structuresref.html)
- [W3C XML 架构数据类型参考（该链接可能指向英文页面）](https://www.xml.com/pub/a/2000/11/29/schemas/dataref.html)
- [XML 架构教程（该链接可能指向英文页面）](https://www.w3schools.com/xml/schema_intro.asp)
- [XML 开发人员中心](https://msdn.microsoft.com/xml/default.aspx)

