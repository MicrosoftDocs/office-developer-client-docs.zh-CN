---
title: 'Parse Function (Access 自定义 Web app) '
manager: kelbow
ms.date: 09/05/2017
ms.audience: Developer
ms.topic: reference
localization_priority: Normal
ms.assetid: 09dee0ae-89b2-449c-a3c8-d6b270710b64
description: 使用应用程序的区域性分析文本值，并返回给定类型中的值。
ms.openlocfilehash: d664985ab1d7a7d33b99c52d5bab4aa714767e40
ms.sourcegitcommit: 8657170d071f9bcf680aba50b9c07f2a4fb82283
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33411132"
---
# <a name="parse-function-access-custom-web-app"></a><span data-ttu-id="56844-103">Parse Function (Access 自定义 Web app) </span><span class="sxs-lookup"><span data-stu-id="56844-103">Parse Function (Access custom web app)</span></span>

<span data-ttu-id="56844-104">使用应用程序的区域性分析文本值，并返回给定类型中的值。</span><span class="sxs-lookup"><span data-stu-id="56844-104">Parses a text value and returns its value in a given type using the culture of the application.</span></span>
  
> [!NOTE]
> <span data-ttu-id="56844-105">本文介绍的云存储功能在 Office 2013 和 Office 2016 中不再受支持，并且可能会导致以下错误：> *抱歉，遇到服务器问题，暂时无法添加 \<service\>。请稍后重试。*</span><span class="sxs-lookup"><span data-stu-id="56844-105">The cloud storage feature described in this article is no longer supported in Office 2013 and Office 2016 and may result in the following error: >  *Sorry, we're having server problems, so we can't add \<service\> right now. Please try again later.*</span></span> <span data-ttu-id="56844-106">> 对于面向 Office Online、Office for iOS 和 Office for Android 的云存储，可以查看我们的 [Office 云存储合作伙伴计划](https://dev.office.com/programs/officecloudstorage)。</span><span class="sxs-lookup"><span data-stu-id="56844-106">> For cloud storage for Office Online, Office for iOS, and Office for Android, you can look into our [Office Cloud Storage Partner Program](https://dev.office.com/programs/officecloudstorage).</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="56844-107">语法</span><span class="sxs-lookup"><span data-stu-id="56844-107">Syntax</span></span>

 <span data-ttu-id="56844-108">**Parse** (*TextExpression*， *DataType*) </span><span class="sxs-lookup"><span data-stu-id="56844-108">**Parse** (*TextExpression*, *DataType*)</span></span> 
  
<span data-ttu-id="56844-109">**Parse** 函数包含下列参数。</span><span class="sxs-lookup"><span data-stu-id="56844-109">The **Parse** function contains the following arguments.</span></span> 
  
|<span data-ttu-id="56844-110">**参数名称**</span><span class="sxs-lookup"><span data-stu-id="56844-110">**Argument name**</span></span>|<span data-ttu-id="56844-111">**说明**</span><span class="sxs-lookup"><span data-stu-id="56844-111">**Description**</span></span>|
|:-----|:-----|
| <span data-ttu-id="56844-112">*TextExpression*</span><span class="sxs-lookup"><span data-stu-id="56844-112">*TextExpression*</span></span>  <br/> |<span data-ttu-id="56844-113">一个文本表达式，代表要解析为指定值的格式数据类型。</span><span class="sxs-lookup"><span data-stu-id="56844-113">A text expression representing the formatted value to parse into the specified data type.</span></span>  <br/> |
| <span data-ttu-id="56844-114">*DataType*</span><span class="sxs-lookup"><span data-stu-id="56844-114">*DataType*</span></span>  <br/> |<span data-ttu-id="56844-115">文本值，数据类型结果请求的值。</span><span class="sxs-lookup"><span data-stu-id="56844-115">Literal value representing the data type requested for the result.</span></span>  <br/> |
   
## <a name="remarks"></a><span data-ttu-id="56844-116">备注</span><span class="sxs-lookup"><span data-stu-id="56844-116">Remarks</span></span>

<span data-ttu-id="56844-117">仅对从字符串转换为日期/时间和数字类型使用 **Parse。**</span><span class="sxs-lookup"><span data-stu-id="56844-117">Use **Parse** only for converting from string to date/time and number types.</span></span> <span data-ttu-id="56844-118">对于常规类型转换，请使用 **Convert** 函数。</span><span class="sxs-lookup"><span data-stu-id="56844-118">For general type conversions, use the **Convert** function.</span></span> <span data-ttu-id="56844-119">请记住，分析字符串值时存在一定的性能开销。</span><span class="sxs-lookup"><span data-stu-id="56844-119">Keep in mind that there is a certain performance overhead in parsing the string value.</span></span> 
  

