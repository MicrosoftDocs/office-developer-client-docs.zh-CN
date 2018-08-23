---
title: 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9e305071-b6a5-4bd8-892e-25553d04bb15
description: 上次修改时间： 2011 年 7 月 23 日
ms.openlocfilehash: 5f372e93457f2b7ef8830ae6bd0363f6b3a7bd60
ms.sourcegitcommit: 0cf39e5382b8c6f236c8a63c6036849ed3527ded
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/23/2018
ms.locfileid: "22581578"
---
# <a name="stream-structures"></a><span data-ttu-id="c4813-103">流结构</span><span class="sxs-lookup"><span data-stu-id="c4813-103">Stream Structures</span></span>

  
  
<span data-ttu-id="c4813-104">**适用于**： Outlook 2013 |Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="c4813-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="c4813-105">[PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中存储的 Microsoft Outlook 项目的用户定义的字段定义。</span><span class="sxs-lookup"><span data-stu-id="c4813-105">Definitions of user-defined fields of a Microsoft Outlook item are stored in the [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md) property.</span></span> <span data-ttu-id="c4813-106">此属性的值是包含用户定义的字段和数据绑定设置对 Outlook 项目的内置字段的定义的二进制流。</span><span class="sxs-lookup"><span data-stu-id="c4813-106">The value of this property is a binary stream that contains definitions of user-defined fields and data-binding settings for built-in fields for the Outlook item.</span></span> <span data-ttu-id="c4813-107">本节提供有关结构的细分以下流结构中的二进制流的信息。</span><span class="sxs-lookup"><span data-stu-id="c4813-107">This section provides information about the structure of the binary stream, broken down in the following stream structures.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c4813-108">这些流结构 （如属性定义、 FieldDefinition 和 SkipBlock） 和其数据元素的名称不技术上一部分的编程接口的消息处理 API (MAPI)，并且仅用于文档此处提供实际流结构的目的。</span><span class="sxs-lookup"><span data-stu-id="c4813-108">The names of these stream structures (for example, PropertyDefinition, FieldDefinition, and SkipBlock) and their data elements are not technically part of the programming interface of the Messaging API (MAPI), and are provided here only for documentation purposes of the actual stream structures.</span></span> <span data-ttu-id="c4813-109">开发人员可以添加标签这些流结构和数据元素的应用程序中，根据他们的选择。</span><span class="sxs-lookup"><span data-stu-id="c4813-109">Developers can label these stream structures and data elements in their applications as they choose.</span></span> 
  
- [<span data-ttu-id="c4813-110">PropertyDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="c4813-110">PropertyDefinition Stream Structure</span></span>](propertydefinition-stream-structure.md)
    
- [<span data-ttu-id="c4813-111">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="c4813-111">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)
    
- [<span data-ttu-id="c4813-112">SkipBlock 流结构</span><span class="sxs-lookup"><span data-stu-id="c4813-112">SkipBlock Stream Structure</span></span>](skipblock-stream-structure.md)
    
- [<span data-ttu-id="c4813-113">FirstSkipBlockContent 流结构</span><span class="sxs-lookup"><span data-stu-id="c4813-113">FirstSkipBlockContent Stream Structure</span></span>](firstskipblockcontent-stream-structure.md)
    
- [<span data-ttu-id="c4813-114">PackedAnsiString 流结构</span><span class="sxs-lookup"><span data-stu-id="c4813-114">PackedAnsiString Stream Structure</span></span>](packedansistring-stream-structure.md)
    
- [<span data-ttu-id="c4813-115">PackedUnicodeString 流结构</span><span class="sxs-lookup"><span data-stu-id="c4813-115">PackedUnicodeString Stream Structure</span></span>](packedunicodestring-stream-structure.md)
    
## <a name="see-also"></a><span data-ttu-id="c4813-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c4813-116">See also</span></span>



[<span data-ttu-id="c4813-117">Outlook 项和字段</span><span class="sxs-lookup"><span data-stu-id="c4813-117">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="c4813-118">为新的用户定义字段添加定义</span><span class="sxs-lookup"><span data-stu-id="c4813-118">Add a Definition for a New User-Defined Field</span></span>](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[<span data-ttu-id="c4813-119">PropertyDefinition 流示例</span><span class="sxs-lookup"><span data-stu-id="c4813-119">PropertyDefinition Stream Sample</span></span>](propertydefinition-stream-sample.md)

