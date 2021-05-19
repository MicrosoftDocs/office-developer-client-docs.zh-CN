---
title: 'Try_Parse Function (Access 自定义 Web 应用) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: ed35263c-b0ad-4269-9caa-c0164015e980
description: 将文本值解析为数据类型区域性中的指定文本值，或返回 Null（如果转换无效）。
ms.openlocfilehash: 5d201557607d2d18c36238d9658b705a6a49fda8
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33427526"
---
# <a name="try_parse-function-access-custom-web-app"></a><span data-ttu-id="14b1a-103">Try_Parse Function (Access 自定义 Web 应用) </span><span class="sxs-lookup"><span data-stu-id="14b1a-103">Try_Parse Function (Access custom web app)</span></span>

<span data-ttu-id="14b1a-104">将文本值解析为数据类型区域性中的指定文本值，或返回 Null（如果转换无效）。</span><span class="sxs-lookup"><span data-stu-id="14b1a-104">Parses a text value to the specified data type in the culture of the application or returns Null if the conversion is not valid.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14b1a-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="14b1a-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="14b1a-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="14b1a-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="14b1a-107">语法</span><span class="sxs-lookup"><span data-stu-id="14b1a-107">Syntax</span></span>

 <span data-ttu-id="14b1a-108">**Try_Parse (** *TextExpression* *、DataType*) </span><span class="sxs-lookup"><span data-stu-id="14b1a-108">**Try_Parse** (*TextExpression*, *DataType*)</span></span> 
  
<span data-ttu-id="14b1a-109">the **Try_Parse** function contains the following arguments.</span><span class="sxs-lookup"><span data-stu-id="14b1a-109">The **Try_Parse** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="14b1a-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="14b1a-110">**Argument name**</span></span>|<span data-ttu-id="14b1a-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="14b1a-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="14b1a-112">*TextExpression*</span><span class="sxs-lookup"><span data-stu-id="14b1a-112">*TextExpression*</span></span>  <br/> |<span data-ttu-id="14b1a-113">一个文本表达式，代表要解析为指定值的格式数据类型。</span><span class="sxs-lookup"><span data-stu-id="14b1a-113">A text expression representing the formatted value to parse into the specified data type.</span></span>  <br/> |
| <span data-ttu-id="14b1a-114">*DataType*</span><span class="sxs-lookup"><span data-stu-id="14b1a-114">*DataType*</span></span>  <br/> |<span data-ttu-id="14b1a-115">用于数据类型  *TextExpression 的字符串*  。</span><span class="sxs-lookup"><span data-stu-id="14b1a-115">The data type into which to parse  *TextExpression*  .</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="14b1a-116">备注</span><span class="sxs-lookup"><span data-stu-id="14b1a-116">Remarks</span></span>

<span data-ttu-id="14b1a-117">Use **Try_Parse** only for converting from string to date/time and number types.</span><span class="sxs-lookup"><span data-stu-id="14b1a-117">Use **Try_Parse** only for converting from string to date/time and number types.</span></span> <span data-ttu-id="14b1a-118">对于常规类型转换，请继续使用 **Convert**。</span><span class="sxs-lookup"><span data-stu-id="14b1a-118">For general type conversions, continue to use **Convert**.</span></span> 
  

