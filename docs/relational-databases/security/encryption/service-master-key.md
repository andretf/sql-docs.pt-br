---
title: "Chave mestra de serviço | Microsoft Docs"
ms.custom: 
ms.date: 03/14/2017
ms.prod: sql-non-specified
ms.prod_service: database-engine
ms.service: 
ms.component: security
ms.reviewer: 
ms.suite: sql
ms.technology:
- database-engine
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service master key [SQL Server]
- service master key [SQL Server], about service master key
ms.assetid: 85f2095d-2590-4f59-8a29-7e100edd02bb
caps.latest.revision: 
author: edmacauley
ms.author: edmaca
manager: craigg
ms.workload: On Demand
ms.openlocfilehash: fbbd6923b2d0bc7158266df1b3d27ecf2c8397cf
ms.sourcegitcommit: 45e4efb7aa828578fe9eb7743a1a3526da719555
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/21/2017
---
# <a name="service-master-key"></a>Chave mestra de serviço
[!INCLUDE[appliesto-ss-xxxx-xxxx-xxx-md](../../../includes/appliesto-ss-xxxx-xxxx-xxx-md.md)] A Chave Mestra de Serviço é a raiz da hierarquia de criptografia do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]. Ela é gerada automaticamente na primeira vez que é necessária para criptografar outra chave. Por padrão, a Chave Mestra do Serviço é criptografada com o uso da API de proteção aos dados do Windows e da chave da máquina local. A chave mestra de serviço só pode ser aberta pela conta de serviço do Windows na qual ela foi criada ou por uma entidade que tenha acesso ao nome e à senha da conta de serviço.  
  
 Gerar novamente ou restaurar a chave mestra de serviço envolve a descriptografia e uma nova criptografia da hierarquia de criptografia completa. Essa operação de uso intensivo de recursos deve ser agendada durante um período de baixa demanda, a menos que a chave mestra esteja comprometida.  
  
 [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] usa o algoritmo de criptografia AES para proteger a SMK (chave mestra de serviço) e a DMK (chave mestra de banco de dados). O AES é um algoritmo de criptografia mais novo que o 3DES usado em versões anteriores. Depois de atualizar uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)] para [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] , o SMK e o DMK devem ser regenerados para atualizar as chave mestras para AES. Para obter mais informações sobre como regenerar a SMK, veja [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](../../../t-sql/statements/alter-service-master-key-transact-sql.md) e [ALTER MASTER KEY &#40;Transact-SQL&#41;](../../../t-sql/statements/alter-master-key-transact-sql.md).  
  
## <a name="best-practice"></a>Prática recomendada  
 Faça backup da chave mestra de serviço e armazene a cópia com backup em um local externo, seguro.  
  
## <a name="related-tasks"></a>Tarefas relacionadas  
 [BACKUP SERVICE MASTER KEY &#40;Transact-SQL&#41;](../../../t-sql/statements/backup-service-master-key-transact-sql.md)  
  
 [RESTORE SERVICE MASTER KEY &#40;Transact-SQL&#41;](../../../t-sql/statements/restore-service-master-key-transact-sql.md)  
  
 [ALTER SERVICE MASTER KEY &#40;Transact-SQL&#41;](../../../t-sql/statements/alter-service-master-key-transact-sql.md)  
  
## <a name="see-also"></a>Consulte também  
 [Hierarquia de criptografia](../../../relational-databases/security/encryption/encryption-hierarchy.md)  
  
  
