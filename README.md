# Bash script for creating react components

## Usage:

- Add scrpt to your path
- cd into directory where you want to create component
- Run script
- Select component type:  
  &nbsp;&nbsp;1) class component  
  &nbsp;&nbsp;2) class component with redux  
  &nbsp;&nbsp;3) stateless component  
  &nbsp;&nbsp;4) stateless component with redux
- Type in component name
- The script will create a directory with the component name with the following files:  
  &nbsp;&nbsp;ComponentName.js  
  &nbsp;&nbsp;ComponentName.styles.js  
  &nbsp;&nbsp;index.js

## Files content:

### index.js

```javascript
import ComponentName from './ComponentName'

export default ComponentName
```

### ComponentName.style.js

```javascript
import { StyleSheet } from 'react-native'

const styles = StyleSheet.create({
  ComponentNameWrapper: {
    flex: 1,
  },
})

export default styles
```

### ComponentName.js (class)

```javascript
import React, { Component } from 'react'
import { View, Text } from 'react-native'
// import propTypes from 'prop-types'

import styles from './ComponentName.styles'

export default class ComponentName extends Component {
  // static propTypes = {
  //   blabla : propTypes.string,
  // }

  // static defaultProps = {
  //   blabla = 'blabla'
  // }

  constructor(props) {
    super(props)
    this.state = {}
  }

  render() {
    return (
      <View style={styles.ComponentNameWrapper}>
        <Text>\$COMPONENT_NAME</Text>
      </View>
    )
  }
}
```

### ComponentName.js (class with redux)

```javascript
import React, { Component } from 'react'
import { View, Text } from 'react-native'
import { connect } from 'react-redux'
// import propTypes from 'prop-types'

import styles from './ComponentName.styles'

class ComponentName extends Component {
  // static propTypes = {
  //   blabla : propTypes.string,
  // }

  // static defaultProps = {
  //   blabla = 'blabla'
  // }

  constructor(props) {
    super(props)
    this.state = {}
  }

  render() {
    return (
      <View style={styles.ComponentNameWrapper}>
        <Text>ComponentName</Text>
      </View>
    )
  }
}

const mapStateToProps = ({ state }) => {
  const { prop } = state
  return { prop }
}

export default connect(mapStateToProps)(ComponentName)
```

### ComponentName.js (stateless)

```javascript
import React from 'react'
import { View, Text } from 'react-native'
// import propTypes from 'prop-types'

import styles from './ComponentName.styles'

const ComponentName = (props) => {
  return (
    <View style={styles.ComponentNameWrapper}>
      <Text>ComponentName</Text>
    </View>
  )
}

// ComponentName.propTypes = {
//   blabla : propTypes.string,
// }

// ComponentName.defaultProps = {
//   blabal: 'blabla'
// }

export default ComponentName
```

### ComponentName.js (stateless with redux)

```javascript
import React from 'react'
import { View, Text } from 'react-native'
import { connect } from 'react-redux'
// import propTypes from 'prop-types'

import styles from './ComponentName.styles'

const ComponentName = (props) => {
  return (
    <View style={styles.ComponentNameWrapper}>
      <Text>ComponentName</Text>
    </View>
  )
}

// ComponentName.propTypes = {
//   blabla : propTypes.string,
// }

// ComponentName.defaultProps = {
//   blabal: 'blabla'
// }

const mapStateToProps = ({ state }) => {
  const { prop } = state
  return { prop }
}

export default connect(mapStateToProps)(ComponentName)
```
