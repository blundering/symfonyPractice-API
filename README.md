# 基于symfony的API

参考文章: [Symfony 4: A quick Demo](https://medium.com/@fabpot/symfony-4-a-quick-demo-da7d32be323)


## 创建项目

$ composer create-project "symfony/skeleton:^3.3" api

- 安装完成
![](https://ws3.sinaimg.cn/large/006tKfTcly1g1e00fx9xyj31b60fsdig.jpg)

## API组件

$ cd api  
$ composer require api

- 安装完成
![](https://ws4.sinaimg.cn/large/006tKfTcly1g1dzxzheifj30yu0o4gox.jpg)

## 添加Entity

- Src\Entity\xxx.php

  <?php  
  namespace App\Entity;  

  use Doctrine\ORM\Mapping as ORM;  
  use ApiPlatform\Core\Annotation\ApiResource;  

  /**  
   * @ORM\Entity  
   * @ORM\Table(name="user")  
   * @ApiResource  
   */  
  class User  
  {  
      /**  
       * @var int the id  
       *   
       * @ORM\Id  
       * @ORM\GeneratedValue  
       * @ORM\Column(type="integer")  
       */  
      public $id;  
    
      /**  
       * @var string A name  
       *   
       * @ORM\Column  
       */  
      public $name;  
  }

- 数据库xxx

  1. .env SQL连接配置  
  2. $ ./bin/console doctrine:database:create  
  3. $ ./bin/console doctrine:scheme:update  
  4. $ /bin/console doctrine:scheme:create

## server组件

$ compoer require server  
$ ./bin/console server:start

- 
![](https://ws1.sinaimg.cn/large/006tKfTcly1g1dzy3p24xj31bu0hon13.jpg)

## 查看使用

$ open http://127.0.0.1:8000/api

- 
![](https://ws2.sinaimg.cn/large/006tKfTcly1g1dzy6kpsuj31gx0u0doh.jpg)

