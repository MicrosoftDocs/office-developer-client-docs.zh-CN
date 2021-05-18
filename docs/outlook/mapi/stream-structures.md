---
title: 流结构
manager: soliver
ms.date: 11/16/2014
ms.audience: Developer
localization_priority: Normal
ms.assetid: 9e305071-b6a5-4bd8-892e-25553d04bb15
description: 上次修改时间：2011 年 7 月 23 日
ms.openlocfilehash: 7f1f1e028797edaa0afb45df4f39aca15ff6d425
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33407821"
---
# <a name="stream-structures"></a><span data-ttu-id="79c79-103">流结构</span><span class="sxs-lookup"><span data-stu-id="79c79-103">Stream Structures</span></span>

  
  
<span data-ttu-id="79c79-104">**适用于**：Outlook 2013 | Outlook 2016</span><span class="sxs-lookup"><span data-stu-id="79c79-104">**Applies to**: Outlook 2013 | Outlook 2016</span></span> 
  
<span data-ttu-id="79c79-105">Microsoft 项目的用户定义字段Outlook存储在[PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md)属性中。</span><span class="sxs-lookup"><span data-stu-id="79c79-105">Definitions of user-defined fields of a Microsoft Outlook item are stored in the [PidLidPropertyDefinitionStream](pidlidpropertydefinitionstream-canonical-property.md) property.</span></span> <span data-ttu-id="79c79-106">此属性的值是一个二进制流，其中包含用户定义的字段的定义以及项目内置字段的数据绑定Outlook设置。</span><span class="sxs-lookup"><span data-stu-id="79c79-106">The value of this property is a binary stream that contains definitions of user-defined fields and data-binding settings for built-in fields for the Outlook item.</span></span> <span data-ttu-id="79c79-107">本节提供有关二进制流结构的信息，这些信息在下列流结构中细分。</span><span class="sxs-lookup"><span data-stu-id="79c79-107">This section provides information about the structure of the binary stream, broken down in the following stream structures.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="79c79-108">这些流结构的名称 (例如 PropertyDefinition、FieldDefinition 和 SkipBlock) 及其数据元素在技术上不是消息 API (MAPI) 编程接口的一部分，并且在此处仅出于实际流结构的文档目的提供。</span><span class="sxs-lookup"><span data-stu-id="79c79-108">The names of these stream structures (for example, PropertyDefinition, FieldDefinition, and SkipBlock) and their data elements are not technically part of the programming interface of the Messaging API (MAPI), and are provided here only for documentation purposes of the actual stream structures.</span></span> <span data-ttu-id="79c79-109">开发人员可以选择在应用程序中标记这些流结构和数据元素。</span><span class="sxs-lookup"><span data-stu-id="79c79-109">Developers can label these stream structures and data elements in their applications as they choose.</span></span> 
  
- [<span data-ttu-id="79c79-110">PropertyDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="79c79-110">PropertyDefinition Stream Structure</span></span>](propertydefinition-stream-structure.md)
    
- [<span data-ttu-id="79c79-111">FieldDefinition 流结构</span><span class="sxs-lookup"><span data-stu-id="79c79-111">FieldDefinition Stream Structure</span></span>](fielddefinition-stream-structure.md)
    
- [<span data-ttu-id="79c79-112">SkipBlock 流结构</span><span class="sxs-lookup"><span data-stu-id="79c79-112">SkipBlock Stream Structure</span></span>](skipblock-stream-structure.md)
    
- [<span data-ttu-id="79c79-113">FirstSkipBlockContent 流结构</span><span class="sxs-lookup"><span data-stu-id="79c79-113">FirstSkipBlockContent Stream Structure</span></span>](firstskipblockcontent-stream-structure.md)
    
- [<span data-ttu-id="79c79-114">PackedAnsiString 流结构</span><span class="sxs-lookup"><span data-stu-id="79c79-114">PackedAnsiString Stream Structure</span></span>](packedansistring-stream-structure.md)
    
- [<span data-ttu-id="79c79-115">PackedUnicodeString 流结构</span><span class="sxs-lookup"><span data-stu-id="79c79-115">PackedUnicodeString Stream Structure</span></span>](packedunicodestring-stream-structure.md)
    
## <a name="see-also"></a><span data-ttu-id="79c79-116">另请参阅</span><span class="sxs-lookup"><span data-stu-id="79c79-116">See also</span></span>



[<span data-ttu-id="79c79-117">Outlook项目和字段</span><span class="sxs-lookup"><span data-stu-id="79c79-117">Outlook Items and Fields</span></span>](outlook-items-and-fields.md)
  
[<span data-ttu-id="79c79-118">添加新字段User-Defined定义</span><span class="sxs-lookup"><span data-stu-id="79c79-118">Add a Definition for a New User-Defined Field</span></span>](how-to-add-a-definition-for-a-new-user-defined-field.md)
  
[<span data-ttu-id="79c79-119">PropertyDefinition Stream 示例</span><span class="sxs-lookup"><span data-stu-id="79c79-119">PropertyDefinition Stream Sample</span></span>](propertydefinition-stream-sample.md)

