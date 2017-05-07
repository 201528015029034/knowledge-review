# JDBC易忘点
JDBC用于在java程序中实现数据库操作。一些使用方法如下(需要记忆)：

  - 加载JDBC驱动器，即com.mysql.jdbc.Driver，放在类路径classpath下，eg:WEB-INF/lib
  - 加载并注册JDBC驱动到DriverManager, 即Class.forName("com.mysql.jdbc.Driver")
  - 使用
  ```sh
  String url = "jdbc:mysql://localhost:3306/databaseName";
  Connection conn = DriverManager.getConnection(url, username, );
  PrepareStatement pstmt = conn.prepareStatement("sql");
  Statement stmt = conn.createStatement("sql");
  ResultSet rs = pstmt.executeQuery();       //rs为对应sql的结果集
  while(rs.next()) {
    System.out.println(rs.getXXX(num));      //XXX为相应类型，num为相应位置
  }
  关闭ResultSet/Statement/Connection
  ```

# 考点

  - statement vs prepareStatement vs CallableStatement
  - 注意释放资源