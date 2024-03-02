## Setup Java Project

### Step 1: Create initial project
```bash
mvn archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes -DarchetypeArtifactId=maven-archetype-quickstart

# cd into dir, or move files


git init && git commit --allow-empty -m "Git Repo Initialized" && \
curl -sL https://www.toptal.com/developers/gitignore/api/java,maven,intellij,eclipse,visualstudiocode > .gitignore && \
git add .gitignore && git commit -m "Create .gitignore" && \
mkdir src/main/resources && touch src/main/resources/.gitkeep && \
mkdir src/test/resources && touch src/test/resources/.gitkeep
```

### Step 2: Update POM

1. Update project ns URIs from http to https, format section
2. Update Java version
3. Bump build plugins to latest version

### Step 3: Add Dependencies

1. Add dependencies
```xml
    <dependency>
      <groupId>org.projectlombok</groupId>
      <artifactId>lombok</artifactId>
      <version>1.18.30</version>
      <scope>provided</scope>
    </dependency>
    <dependency>
      <groupId>org.apache.commons</groupId>
      <artifactId>commons-lang3</artifactId>
      <version>3.14.0</version>
    </dependency>

    <dependency>
      <groupId>org.junit.jupiter</groupId>
      <artifactId>junit-jupiter</artifactId>
      <version>5.9.2</version>
      <scope>test</scope>
    </dependency>
    <dependency>
      <groupId>org.mockito</groupId>
      <artifactId>mockito-core</artifactId>
      <version>4.8.1</version>
      <scope>test</scope>
    </dependency>
    <dependency>
      <groupId>org.mockito</groupId>
      <artifactId>mockito-junit-jupiter</artifactId>
      <version>4.8.1</version>
      <scope>test</scope>
    </dependency>
    <dependency>
      <groupId>org.hamcrest</groupId>
      <artifactId>hamcrest</artifactId>
      <version>2.2</version>
      <scope>test</scope>
    </dependency>
    <dependency>
      <groupId>org.assertj</groupId>
      <artifactId>assertj-core</artifactId>
      <version>3.23.1</version>
      <scope>test</scope>
    </dependency>

```

#### Step 4: Fix AppTest.java

```java
import static org.assertj.core.api.Assertions.assertThat;

import org.assertj.core.api.Assertions.*;
import org.hamcrest.Matchers.*;
import org.junit.jupiter.api.Test;
import org.mockito.Mockito.*;

/**
 * Unit test for simple App.
 */
public class AppTest 
{
    /**
     * Rigorous Test :-)
     */
    @Test
    public void shouldAnswerWithTrue()
    {
        assertThat(true).isTrue();
    }
}

```

#### Step 5: Commit


```bash
git add -A . && git commit -m "Initial setup for project "
```

## Alternative: Spring Boot Setup

https://start.spring.io/#!type=maven-project&language=java&dependencies=devtools,configuration-processor,lombok
