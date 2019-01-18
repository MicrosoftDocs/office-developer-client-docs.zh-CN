---
title: Attributes 属性 (ADOX)
TOCTitle: Attributes property (ADOX)
ms:assetid: d5227b10-4a9b-5a57-d5ab-bbdd3e89aa95
ms:mtpsurl: https://msdn.microsoft.com/library/JJ250072(v=office.15)
ms:contentKeyID: 48547959
ms.date: 09/18/2015
mtps_version: v=office.15
localization_priority: Normal
ms.openlocfilehash: 14a4c719723767be8cb8e7e2f8ed02b5d2d4a143
ms.sourcegitcommit: d6695c94415fa47952ee7961a69660abc0904434
ms.translationtype: Auto
ms.contentlocale: zh-CN
ms.lasthandoff: 01/17/2019
ms.locfileid: "28698167"
---
# <a name="attributes-property-adox"></a><span data-ttu-id="d016e-102">Attributes 属性 (ADOX)</span><span class="sxs-lookup"><span data-stu-id="d016e-102">Attributes property (ADOX)</span></span>


<span data-ttu-id="d016e-103">**适用于**： Access 2013、 Office 2013</span><span class="sxs-lookup"><span data-stu-id="d016e-103">**Applies to**: Access 2013, Office 2013</span></span>

<span data-ttu-id="d016e-104">描述列的特征。</span><span class="sxs-lookup"><span data-stu-id="d016e-104">Describes column characteristics.</span></span>

## <a name="settings-and-return-values"></a><span data-ttu-id="d016e-105">设置和返回值</span><span class="sxs-lookup"><span data-stu-id="d016e-105">Settings and return values</span></span>

<span data-ttu-id="d016e-p101">设置或返回一个 **Long** 值。该值指定 [Column](column-object-adox.md) 对象所表示的表的特征，并且可为多个 [ColumnAttributesEnum](columnattributesenum.md) 常量的组合。默认值为零 (0)，表示既不是 **adColFixed** ，也不是 **adColNullable** 。</span><span class="sxs-lookup"><span data-stu-id="d016e-p101">Sets or returns a **Long** value. The value specifies characteristics of the table represented by the [Column](column-object-adox.md) object and can be a combination of [ColumnAttributesEnum](columnattributesenum.md) constants. The default value is zero (0), which is neither **adColFixed** nor **adColNullable**.</span></span>

