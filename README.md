# crown

repositories{
  maven{
    url ''
  }
}


configurations.all{
  resolutionStrategy{
    failOnVersionConflict()
    //force 'org.slf4j-api:1.7.24'
  }
}

# 强制性依赖

configurations.all{
  resolutionStrategy{
    force 'org.slf4j-api:1.7.24'
  }
}


# 排除传递性依赖

compile('org.hibernate:hibernate-core:3.6.3.Final'){
  exclude group:"org.slf4j" ,module:"slf4j-api"  
  // transitive=false
}

